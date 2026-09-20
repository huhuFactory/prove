---
type: Policy
title: IceT Data Integrity 정책
status: draft
sources:
  - id: user-data-integrity-2026-09-20
    description: 2026-09-20 사용자가 제공한 IceT Data Checker 동작 및 Test Case 작성 정책 설명
generated: { by: openai-codex, at: "2026-09-20" }
---

# IceT Data Integrity 정책

Test Case 작성 시 필요한 Data Checker의 기본 동작, 명령별 예상 상태와 비교 비활성화 시 처리 방법을 정리한다. 올바른 데이터 검증과 명시적인 검증 제외 범위를 통해 Test 결과와 실행 Evidence의 신뢰성을 높이는 것이 목적이다.

이 문서는 사용자 설명을 정리한 초안이다. IceT 코드와 특정 버전에 대한 대조 검토는 아직 수행하지 않았다. 회사 프로젝트의 동작 정책과 NVMe 규격의 일반 요구 사항을 구분한다.

## 1. 기본 검사 정책

IceT는 기본적으로 Data Integrity 검사를 활성화한다. 다음 설정으로 비교를 비활성화할 수 있다.

| 적용 범위 | 설정 |
|---|---|
| IceT 시작 시 | `--disableDataChecking` |
| 개별 I/O API 호출 시 | `Compare` 옵션을 `false`로 설정 |

검사가 활성화되어 있어도 모든 Read의 데이터가 비교되는 것은 아니다. Data Checker가 해당 명령을 지원하고, 대상 LBA에 비교 가능한 예상 상태가 기록되어 있어야 한다. 초기 상태가 `비교 안 함`인 LBA와 일부 예외 명령은 검사 대상에서 제외된다.

옵션의 정확한 API 표기, 명령별 적용 범위와 비활성화 시 내부 상태 갱신 여부는 추가 확인이 필요하다.

## 2. 검출 대상

| 유형 | 의미 |
|---|---|
| 다른 LBA의 데이터 반환 | LBA X를 읽었는데 다른 LBA에 해당하는 데이터가 반환됨 |
| 동일 LBA의 과거 데이터 반환 — Stale Data | LBA X의 마지막 Write 데이터 대신 그 이전 Write 데이터가 반환됨 |
| 기타 데이터 손상 — Data Corruption | Bit Flip, 일부 데이터 유실 등 위 두 유형 외의 데이터 손상 |

이는 Data Checker가 확인하려는 문제 유형이다. 모든 유형을 모든 조건에서 검출한다는 보장이나 검출률을 정의하지는 않는다. 패턴 생성 방식과 검출 한계는 추후 설명이 필요하다.

## 3. Data Checker의 상태 관리

Data Checker는 데이터 Read/Write와 관련된 명령을 처리하는 별도 모듈이다. 기본 I/O는 지원하지만 모든 명령을 예외 없이 처리하지는 않는다. 전체 지원 목록과 예외 목록은 아직 제공되지 않았다.

### LBA별 메모리

Device의 각 LBA와 1:1로 대응하는 상태 메모리를 사용한다.

| 모드 | LBA당 상태 메모리 |
|---|---|
| 기본 모드 | 1 byte |
| nibble 모드 | 4 bits |

위 수치는 LBA별 상태 메모리에 대한 설명이며 Data Checker 전체 메모리 사용량을 의미하지 않는다.

### 시작 시 상태

IceT 시작 시 모든 LBA의 Data Checker 상태는 초기화되어 `비교 안 함`으로 설정된다. 이 상태에서 Read하면 반환 데이터의 내용은 비교하지 않는다.

사용자 설명상 이때 Read 명령의 성공·실패는 완료 상태의 SC(Status Code)와 SCT(Status Code Type)로 판단한다. 명령 완료 성공은 데이터 내용의 무결성 검증 완료를 의미하지 않는다.

여기서 초기화는 **Data Checker의 추적 상태 초기화**를 뜻한다. Device 데이터 초기화나 NVMe Reset 명령을 뜻하지 않는다.

## 4. 명령별 예상 상태와 Read 검사

데이터 또는 예상 상태를 변경하는 명령이 수행되면 Data Checker는 **그 명령의 대상 LBA들**에 관련 상태를 기록한다. 전체 Device의 모든 LBA를 매번 갱신한다는 의미는 아니다.

상태 갱신이 명령 제출 시점인지 완료 시점인지, 실패한 명령과 동시 실행 명령을 어떻게 처리하는지는 아직 설명되지 않았다.

| 명령 | Data Checker 처리 | 이후 Read 시 검사 |
|---|---|---|
| Write | Write 명령마다 난수를 추출하고 특정 데이터 패턴 생성 | 생성한 패턴에 따른 예상 데이터와 비교. 패턴 구성은 추후 추가 |
| Write Uncorrectable (`WriteUnc`) | 대상 LBA를 Write Uncorrectable 상태로 표시 | 예상한 UECC 오류가 발생하면 Pass로 처리할 수 있도록 함 |
| Write Zeroes | 대상 LBA를 Write Zeroes 상태로 표시 | `0x00`과 비교 |
| Dataset Management의 Deallocate — 이하 DSM Trim | 대상 LBA를 Trim 상태로 표시 | `0x00`과 비교 |
| Copy | 사용자 설명상 추적 대상에 포함 | 원본·대상 LBA 상태의 반영 규칙은 추후 추가 |

### Write Uncorrectable

Write Uncorrectable 이후의 Read에서는 정상 데이터 반환이 아니라 예상 오류 발생 여부를 확인한다. `UECC`는 사용자 설명의 용어를 유지했다. 정확히 어떤 SC/SCT 조합을 예상 오류로 인정하는지와 범위가 섞인 Read의 판정은 확인이 필요하다. 임의의 Read 오류를 Pass로 인정한다는 의미는 아니다.

### Write Zeroes와 DSM Trim

현재 회사 프로젝트는 Write Zeroes 또는 DSM Trim 대상 영역의 Read 데이터가 `0x00`이 되도록 정하고 있으며, IceT도 이를 기준으로 비교한다.

이 문서에서는 이를 **현재 회사 프로젝트의 기대 동작**으로 기록한다. 모든 NVMe Device와 모든 옵션에 적용되는 규격상 보장으로 일반화하지 않는다. 사용자 설명에 포함된 “Spec.상 다른 값이 반환될 수 있다”의 정확한 조건과 적용 규격 버전은 추가 확인이 필요하다.

## 5. 큰 범위의 DSM Trim

DSM Trim 범위가 크면 Data Checker가 대상 LBA 각각의 상태를 변경하는 데 많은 시간이 걸릴 수 있다. Namespace 전체를 대상으로 할 때도 같은 문제가 발생할 수 있다.

사용자가 제시한 Test Case 작성 권장 사항은 다음과 같다.

1. 큰 LBA 범위 또는 Namespace 전체에 DSM Trim을 수행할 때는 성능을 고려해 DSM API의 `Compare` 옵션을 끈다.
2. 이후 별도 Data Checker API를 사용해 해당 Namespace의 예상 상태를 `0x00 비교` 또는 `비교 안 함`으로 설정한다.
3. `비교 안 함`을 선택했다면 이후 Read가 데이터 내용의 무결성을 검증하지 않는다는 점을 Test 결과 해석에 반영한다.

여기서 Namespace는 영역을, NSID는 그 Namespace를 식별하는 값을 뜻한다. “NSID 영역”은 이 문서에서 “해당 Namespace 영역”으로 정리했다.

큰 범위의 판단 기준, 구체적인 API 이름과 상태 갱신 비용은 아직 제공되지 않았다. 별도 API가 즉시 Read를 실행한다는 의미가 아니라, 이후 Read에 사용할 Data Checker의 예상 상태를 설정한다는 설명이다.

## 6. Sanitize 이후의 수동 상태 갱신

사용자 설명상 IceT는 Sanitize 수행에 맞춰 Data Checker 상태를 자동 갱신하지 않는다. 넓은 영역의 LBA별 상태 갱신 비용 때문에, Sanitize 완료 후 사용자가 원하는 시점에 Data Checker API로 Namespace별 예상 상태를 설정한다.

| Sanitize 후 사용할 검사 방식 | 사용자가 수행할 설정 |
|---|---|
| `0x00` 비교 | 해당 Namespace의 예상 상태를 `0x00 비교`로 설정 |
| 데이터 비교 생략 | 해당 Namespace의 예상 상태를 `비교 안 함`으로 설정 |
| Sanitize Overwrite 패턴 비교 | 해당 Namespace에 Sanitize Overwrite 상태와 사용한 Overwrite 값을 등록 |

`0x00 비교`는 적용 프로젝트와 Sanitize 방식의 기대 결과에 맞게 선택해야 한다. 모든 Sanitize가 자동으로 데이터를 `0x00`으로 만든다는 의미는 아니다.

### Sanitize Overwrite

- IceT가 Sanitize 명령 처리 중 Overwrite 비교 상태를 자동으로 설정하지 않는다.
- Sanitize 완료 후 사용자가 Data Checker API에 Overwrite 수행 사실과 사용한 값을 전달한다.
- Data Checker는 각 대상 LBA에 Sanitize Overwrite 상태를 기록한다.
- 이후 해당 LBA를 Read하면 등록된 Overwrite 값과 비교한다.
- 현재 사용자 설명상 IceT는 **4-byte Sanitize Overwrite 값만 지원**한다. 패턴 반복 방식과 추가 옵션 처리는 아직 설명되지 않았다.

### Sanitize 적용 범위에 관한 확인 사항

원래 설명은 “Sanitize는 NS 단위이며 무조건 NS 단위”였다. 이 문서에서는 **IceT Data Checker 상태를 Namespace별로 갱신한다는 설명**과 **NVMe Sanitize 명령 자체의 적용 범위**를 분리한다.

NVM Express의 [Sanitize 소개](https://nvmexpress.org/changes-in-nvme-revision-1-3/)는 NVM subsystem 전체 사용자 데이터를 대상으로 설명한다. 따라서 “무조건 NS 단위”는 일반 규칙으로 확정하지 않는다. 회사에서 적용하는 규격 버전, Sanitize 종류와 IceT API의 범위를 확인해야 한다.

## 7. Test Case 작성 시 확인할 내용

- 해당 I/O에서 비교가 활성화되어 있는가?
- Read 대상 LBA가 `비교 안 함` 상태인가, 비교 가능한 예상 상태인가?
- 예상 결과가 정상 데이터인가, Write Uncorrectable에 따른 예상 오류인가?
- 큰 DSM Trim 또는 Sanitize 후 Data Checker 상태를 필요한 검사 방식에 맞게 설정했는가?
- `0x00`이나 Overwrite 값이 해당 프로젝트·명령의 실제 기대 결과와 일치하는가?

## 8. 다음 설명에서 보완할 사항

- Write의 난수와 데이터 패턴 생성 방식, Stale Data 검출 한계
- Copy의 원본·대상 상태 처리
- 지원 명령과 예외 명령의 전체 목록
- 옵션의 정확한 API 표기와 비교 비활성화 시 상태 갱신 여부
- 상태 갱신 시점, 실패·중첩·동시 실행 명령 처리
- Write Uncorrectable Read의 기대 SC/SCT와 혼합 범위 처리
- 기본 모드와 nibble 모드의 의미·제약 차이
- DSM·Sanitize 후 사용하는 Data Checker API와 호출 조건
- Sanitize의 적용 범위, 4-byte Overwrite 패턴과 관련 옵션 처리
- 적용 IceT 버전, 회사 프로젝트 범위와 규격 버전
