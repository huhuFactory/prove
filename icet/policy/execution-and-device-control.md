---
type: Policy
title: IceT 실행 및 Device 제어 정책
status: draft
sources:
  - id: user-device-reset-2026-09-21
    description: 2026-09-21 사용자가 설명한 Device 전원 반복 차단·복구 및 Reset 중 IceT 실행 유지
  - id: user-policy-separation-2026-09-21
    description: 2026-09-21 사용자가 실행 동작 설명을 Data Checker 정책과 별도 파일로 분리하도록 요청
generated: { by: openai-codex, at: "2026-09-21" }
---

# IceT 실행 및 Device 제어 정책

Test Case에서 Device 전원과 Reset을 제어할 때의 IceT 실행 방식을 정리한다. Device의 상태 변화 중에도 테스트를 수행하는 실행 구조를 명확히 하여 검증 절차와 결과를 이해하는 데 활용한다.

## Device 전원 제어와 Reset

전원 차단·복구 및 Reset 테스트에서는 **IceT를 종료하지 않고 실행 상태로 유지한 채 Device의 전원을 껐다 켜거나 Device를 Reset한다.** Device 재시작을 IceT 재시작과 동일하게 취급하지 않는다.

이 설명은 IceT 실행 유지에 관한 정책이다. 개별 모듈의 내부 상태까지 모두 유지된다는 의미로 확대하지 않는다. Data Checker의 추적 상태와 중단된 명령 처리는 [Data Integrity 정책](data-integrity.md)의 확인 사항으로 관리한다.
