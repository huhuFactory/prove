---
type: Principle
title: Stateful Test Sequencing
description: Stable rules for Test state reuse, explicit dependencies, and sequence-dependent Failure analysis.
tags: [prove, state, test-case, sequencing, failure, traceability]
status: stable
sources:
  - id: stateful-sequence-directive-2026-08-02
    resource: /sources/stateful-test-sequence-directive-2026-08-02.md
    title: PROVE leader Stateful Test Sequence directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
verified: { by: "human:prove-leader", at: "2026-08-02T00:00:00+09:00" }
---

# Core Rule

> **State reuse is allowed; hidden dependency is not.**

PROVE does not require unconditional full initialization between Test Cases. It requires the starting state of every Case to be declared and demonstrated.

A transition from Case A to Case B is valid when A's observed Post-State satisfies B's required Pre-State:

```text
Observed Post-State(A) satisfies Required Pre-State(B)
```

Labels such as `Clean` and `Dirty` are insufficient by themselves. Relevant Device, Host, platform, data, configuration, workload-history, recovery, and environmental state must be represented at the granularity needed by the Scenario.

# Logical Independence and Physical Reuse

A Case may physically reuse a state created by an earlier Case while remaining logically independent of that Case's identity. Prefer:

```text
Case A produces State-X
Case B requires a State-X-compatible state
```

Avoid an unexplained rule such as `B must run after A`. If A's exact behavior is part of what B verifies, model the combined flow as one Test Case or an explicit stateful sequence.

# Sequence-Dependent Failure

A Failure observed in Case C may have been created or activated by earlier Cases:

```text
Case A creates a latent state
→ Case B preserves or transforms it
→ Case C exposes the Failure
```

The observation point is not automatically the causal point. A sequence-dependent finding is valid even when the discovery order was accidental.

PROVE should preserve Evidence before recovery and compare controlled sequences such as:

```text
Baseline → C
A → C
B → C
A → B → C
A → Reset → C
```

The goal is to identify the minimal necessary state transition and distinguish Device Failure from Test, IceT, Host, environment, or orchestration problems.

# Asset Promotion

When a meaningful sequence is reproduced and minimized, PROVE should convert it into traceable verification knowledge:

```text
New or refined Test Scenario
→ minimal state-transition Test Case
→ replaceable Test Script
→ replayable Evidence and regression asset
```

The resulting Case records the required Pre-State, state-changing actions, relevant intermediate states, Oracle, Evidence, Post-State, and cleanup or preservation policy.

# Scheduling Consequences

- A scheduler may reuse compatible states to reduce expensive preparation.
- It must verify state compatibility before starting the next Case.
- A failed or uncertain Case invalidates assumptions about its Post-State until Evidence proves otherwise.
- Execution order, state lineage, configuration, and relevant state observations are part of the run record.
- Optimization must not introduce an undeclared dependency.

# Decision Boundary

The exact State schema, observability requirements, compatibility algorithm, and state-transition Coverage method remain open. This principle does not approve a Coverage axis or a specific scheduler implementation.
