---
type: Source Summary
title: Two-Month Work Items 6–11 Review Input — 2026-08-02
description: Preserved review input for PROVE two-month work items 6 through 11 and the consolidated workstream map.
tags: [prove, source, two-month, work-items, execution, failure, governance]
status: stable
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
verified: { by: "human:prove-leader", at: "2026-08-02T00:00:00+09:00" }
---

# Document Status

This document preserves the review input supplied by the PROVE leader so that work can continue after context compression. Storage here confirms the input text, not approval of every proposed work item or model. Items 6 through 11 must be reviewed one at a time before they are treated as agreed direction.

The step-by-step review was subsequently completed on 2026-08-02. Current decisions and remaining unknowns are synthesized in the [Two-Month Integrated Execution Framework](/project/two-month-execution-framework.md); this Source remains the historical input and is not rewritten as the current plan.

# 6. 실행 가능성 검증

생성된 Test의 평가는 문서나 코드 분석으로 끝나면 안 됩니다.

```text
생성
→ Syntax/Build 검증
→ API 사용 검증
→ 실제 Hardware 실행
→ Timeout·Crash·Flaky 여부 확인
→ Expected/Actual Result 평가
→ Cleanup과 Recovery 확인
```

특히 다음을 별도로 측정해야 합니다.

- Test 자체가 실행 가능한가
- Test가 Scenario의 의도를 구현했는가
- Test의 판정 조건이 충분한가
- 반복 실행 결과가 재현 가능한가
- IceT가 Reset과 Error 상황에서도 통제권을 유지하는가

# 7. 실행 환경 Applicability 모델

기존에는 Hardware와 PCIe 세대, 제품군의 관계가 불명확했습니다. 미래 Test에는 이를 반복하면 안 됩니다.

Test가 특정 Hardware 이름을 직접 지정할지, 필요한 Capability를 선언할지는 결정되지 않았지만 최소한 다음 개념은 필요합니다.

- 필요한 Hardware Capability
- PCIe/NVMe 조건
- 대상 제품군
- FW 및 Spec Version
- Sideband 기능
- Error Injection 요구사항
- 실행 전제조건

이 정보로 SkyTower나 실행 Agent가 적절한 환경을 선택할 수 있어야 합니다.

# 8. Failure 분석과 진성·가성 평가

2개월 Milestone의 필수 범위이므로 별도 작업으로 명시해야 합니다.

```text
Fail 발생
→ 재현
→ Evidence 수집
→ Device/Non-device/Unknown 판정
├─ Device: BRAIN 이관
├─ Non-device Test: 수정·검증·재실행
├─ Non-device 환경: 복구·재실행
└─ Unknown: 사람 개입
```

필요한 세부 작업은 다음입니다.

- 진성·가성 판정 기준
- 대표 평가 Dataset
- 재현 전략
- 판정 신뢰도
- Unknown 처리
- 자동 수정·복구 한도
- BRAIN Handoff Package

# 9. Knowledge 확장과 Governance

말씀하신 사용자의 권한은 단순한 접근 권한보다 큰 주제입니다.

사용자가 자신의 노하우를 추가할 수 있어야 하지만, 바로 전사 공통 지식이 되면 위험합니다. 예를 들면 다음 계층이 필요할 수 있습니다.

```text
Global Verified Knowledge
└─ Team Knowledge
   └─ Project Knowledge
      └─ User Draft Knowledge
```

결정해야 할 내용:

- 사용자가 어떤 지식을 추가할 수 있는가
- 다른 사용자가 볼 수 있는가
- 누가 검증하는가
- 언제 Global Knowledge로 승격되는가
- 기존 지식과 충돌하면 어떻게 하는가
- 잘못된 지식을 폐기하거나 되돌리는 방법

정확한 계층은 아직 제안 단계이며 TF 논의가 필요합니다.

# 10. Agent 운영과 재현성

배포 방식과 함께 다음도 필요합니다.

- Agent와 Prompt Version
- 사용한 Model
- 조회한 Knowledge
- Tool 호출 기록
- 생성한 Artifact
- Agent 간 Handoff
- Retry와 중단 조건
- 비용과 실행 시간
- 실패 시 재개 지점
- 동일 입력에 대한 재현 방법

Agent가 결과만 남기면 나중에 왜 그런 Requirement나 Scenario가 나왔는지 설명할 수 없습니다.

# 11. 생성 Test의 Version과 공식 반영

생성된 Test가 동작한다고 바로 공식 Package에 들어가는 것은 아닙니다.

```text
Generated
→ Validated
→ Executed
→ Coverage Evaluated
→ Candidate
→ Official
→ Deprecated
```

각 상태와 다음 항목이 필요합니다.

- Test Version
- 적용 Package
- 검증 결과
- 기존 Test와의 관계
- Rollback
- 수정 이력
- 공식 Package 승격 조건

# Consolidated Workstreams

## Knowledge Foundation

- 지식 선정과 축적
- 공통 Verification Knowledge Model
- 지식 확장 및 Governance
- Source/Version/Change Impact

## Extraction and Scenario

- Spec 기반 Requirement 추출
- 기존 Package Dependency 분석
- 기존 Test에서 Scenario와 노하우 추출
- FLAIR 기반 Requirement와 Scenario 추출
- Scenario 정규화·중복·충돌 처리

## Coverage and Evaluation

- Verification Space와 Coverage 기준
- Golden Dataset과 평가 Harness
- 기존 Package Coverage 분석
- 생성 Scenario 및 Test 품질 평가

## Generation and Execution

- Test 생성
- 정적·Build 검증
- 실제 Hardware 실행
- 실행 환경 Applicability
- 재현성과 Flaky 분석

## Failure and Feedback

- Pass/Fail
- 진성·가성·Unknown
- Test 수정 및 환경 복구
- BRAIN 이관
- 실행 결과의 Knowledge Feedback

## Platform and Operation

- Agent 배포
- 사용자 권한과 Knowledge 확장
- Traceability
- Agent 관측·재현·감사
- Test Version과 공식 Package 반영

# Mandatory Additions Proposed in the Input

핵심적으로는 현재 목록에 다음 네 가지를 반드시 추가하는 것이 좋습니다.

- 공통 Verification Knowledge Model
- Golden Dataset 및 Evaluation Harness
- 실제 실행과 진성·가성 분석
- Knowledge/Test Lifecycle 및 Feedback Loop

# Relationship to Existing Package Coverage

Requirements → Scenario 추출 시 기존 Package Coverage가 필요한가에 대해서는, 현재 PROVE의 Core Value를 기준으로 보면 필요합니다.

다만 기존 Package가 새 Scenario의 상한선을 결정해서는 안 됩니다.

```text
Spec Requirement에서 기본 Scenario 도출
+ 기존 Package에서 Verification Intent와 노하우 추출
+ Coverage Gap에서 추가 Scenario 도출
```

즉 기존 Package는 보존해야 할 기준이자 지식 원천이지만, 새로운 검증 공간을 제한하는 기준은 아닙니다.
