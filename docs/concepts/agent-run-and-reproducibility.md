---
type: Concept Model
title: Agent Run and Reproducibility Model
description: Working identity model for tracing every PROVE Agent attempt, Hardware execution, retry, resume, and Failure investigation.
tags: [prove, agent, workflow, run, retry, reproducibility]
status: draft
sources:
  - id: agent-run-hierarchy-directive-2026-08-02
    resource: /sources/agent-run-hierarchy-directive-2026-08-02.md
    title: Agent Run hierarchy directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Identity Hierarchy

```text
Verification Request
└─ Agent Workflow Run
   ├─ Agent steps, decisions, Handoffs, and Artifacts
   ├─ Retry or resumed Workflow Run → new linked Attempt
   └─ Test Execution Run
      ├─ Re-execution → new linked Run
      └─ Fail → Failure Analysis Record
```

- **Verification Request** identifies the requested verification outcome and context.
- **Agent Workflow Run** identifies one attempt to process that Request through a versioned Agent workflow.
- **Test Execution Run** identifies one execution of a Test on real Hardware and its exact environment.
- **Failure Analysis Record** identifies the investigation that follows an observed Fail.

# Immutability and Lineage

Retry, resume, regeneration, and re-execution append new linked Attempts rather than overwriting prior state. The relationship records why the later Attempt occurred and from which checkpoint or predecessor it derived.

Changing a Model, Prompt, Agent workflow, Knowledge set, Tool, generated Artifact, or execution configuration produces a distinct Run identity. A comparison may relate the Runs, but it must not make them appear to be the same attempt.

# Minimum Workflow Evidence

Each Agent Workflow Run must be able to reference:

- Parent Verification Request and applicable Baseline
- Agent, workflow, Model, Prompt, Knowledge, and Tool versions
- Inputs, retrieved Sources, decisions, Handoffs, and state transitions
- Generated Artifacts and content identities
- Retry, interruption, resume, and exit reasons
- Cost, elapsed time, and resource use when available
- Child Test Execution Runs, Evidence, verdicts, and Failure Analysis Records

The detailed event schema, checkpoint format, storage, and retention policy remain open.

# Reproducibility Levels

PROVE uses three complementary meanings of reproducibility:

1. **Audit reproducibility**: reconstruct the exact Request, Source, Knowledge, Agent, Model, Prompt, Tool, decision, Artifact, environment, and event history.
2. **Operational replay**: rerun a Workflow or Test with pinned versions and configuration when those dependencies remain available.
3. **Verification-result equivalence**: demonstrate that a regenerated output preserves the Scenario intent and satisfies the applicable quality and Evidence criteria even when its text or code is not byte-identical.

LLM output is not assumed to be byte-identical across Runs. Deterministic steps and content-addressed Artifacts may require exact identity where their contracts specify it. Any unavailable Model, Tool, Source, or environment that prevents exact replay must be reported rather than silently substituted.

# Artifact Handoff and Checkpoint

Agent Handoffs use versioned Artifact identities and supporting Evidence rather than only a message or conversation summary. Candidate durable boundaries include the Verification Request, Requirement set, Scenario set, Test Case, validation result, Execution Plan, Execution Evidence, and Failure Analysis Record.

When a Workflow is interrupted:

1. Preserve the interrupted Run and reason.
2. Create a new linked Attempt.
3. Verify that the selected Checkpoint and all upstream inputs remain valid.
4. Resume from the last valid boundary, or recompute from the earliest boundary affected by an upstream change.

Retry is bounded. Every attempt records its cause, policy, inputs, outputs, and exit condition. The exact Checkpoint granularity, retry limits, and escalation policy remain open.
