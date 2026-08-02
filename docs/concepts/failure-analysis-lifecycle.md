---
type: Concept Model
title: Failure Analysis Lifecycle
description: Working PROVE lifecycle that separates observed Test Verdict from evidence-based Failure Disposition and follow-up action.
tags: [prove, failure-analysis, verdict, disposition, brain]
status: draft
sources:
  - id: failure-analysis-agent-directive-2026-08-02
    resource: /sources/failure-analysis-agent-directive-2026-08-02.md
    title: PROVE Failure Analysis Agent directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# State Separation

A Test Verdict describes what execution observed against its Oracle. A Failure Disposition describes PROVE's later conclusion about the responsible domain. They must not be represented as one state.

```text
Test execution
→ Test Verdict
   ├─ Pass → record Evidence and Coverage contribution
   └─ Fail → trigger PROVE Failure Analysis Agent
                 ↓
            Failure Disposition
            ├─ Device
            ├─ Non-device
            └─ Unknown
```

A Fail is not itself proof of an SSD defect. The Failure Analysis Agent must preserve the link to the original Verification Request, Scenario, Case, Script, Run, environment, and Evidence.

# Evidence Before Intervention

The first-Failure Evidence must be captured and made immutable before Reset, recovery, rerun, repair, or diagnostic action changes the Device or environment state. Later attempts extend the Evidence lineage; they do not replace the first observation.

# Adaptive Reproduction

Reproduction is an analysis strategy, not one fixed prerequisite applied identically to every Failure. The Failure Analysis Agent plans whether, how, and how often to reproduce based on preserved Evidence, Device and environment state, known signatures, and analysis needs.

- Record every reproduction attempt and result.
- Record why reproduction was skipped, changed, or stopped.
- Treat non-reproduction as Evidence, not automatic proof of either Device or Non-device cause.
- Keep the Disposition `Unknown` when available Evidence is insufficient.

# Failure Analysis Record

Each observed Test Fail creates a versioned Failure Analysis Record with a stable identity. It is the aggregate Traceability unit for:

- Original failed Run and immutable first-Failure Evidence
- Reproduction plan, attempts, results, and stopping rationale
- Agent hypotheses, Tool use, retrieved Knowledge, and diagnostic runs
- Disposition and confidence-history changes
- Test repair, IceT repair, Host or environment recovery, and reruns
- BRAIN handoff package, downstream analysis, and returned reclassification
- Human escalation, intervention, and final closure

The Record evolves by appending or versioning analysis state rather than overwriting history. Similar Failures may later be linked to a common signature or cluster, but each occurrence retains its own Record until an approved deduplication and causal model exists.

# PROVE Agent Boundary

The Failure Analysis Agent is a logical Agent capability inside PROVE. Its internal decomposition and implementation framework are not yet selected.

- **Device**: prepare traceable Evidence and hand off automatically to BRAIN under the approved contract.
- **Non-device**: identify its category and invoke the applicable Test repair, IceT repair, Host or environment recovery, validation, and rerun flow.
- **Unknown**: preserve uncertainty and request human intervention according to the later confidence and escalation policy.

BRAIN performs downstream SSD firmware Failure analysis. It may return a reclassification to PROVE, which must remain part of the same Failure lineage.

# Device Disposition Basis

PROVE decides whether a Failure should be treated as a Device problem from the Host and verification-system perspective. It is not required to prove the internal SSD root cause before BRAIN handoff.

A Device Disposition may be supported by either:

- Direct Evidence that the Device violated defined behavior; or
- A remaining defined Device-behavior violation after Test, Oracle, IceT, Host, environment, configuration, and other plausible Non-device causes have been reasonably investigated and excluded.

`No Non-device cause found after adequate analysis` is different from `Non-device causes could not be observed or analyzed`. The latter remains `Unknown` when the Evidence is insufficient. The detailed sufficiency criteria are deliberately deferred.

# Open Design

The Failure Analysis Record schema, required Evidence set, adaptive-reproduction policy details, disposition criteria, confidence representation, representative evaluation Dataset, retry and repair limits, Unknown escalation, clustering model, and BRAIN Handoff Package remain to be defined.
