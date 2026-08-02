---
type: Principle
title: Traceability and Reproducibility
description: Required lineage from source knowledge through generated tests and failure disposition.
tags: [prove, traceability, reproducibility, audit]
status: draft
sources:
  - id: discovery-2026-07-26
    resource: /sources/discovery-interview-2026-07-26.md
    title: PROVE leader discovery discussion
    author: human:prove-leader
    last_modified: 2026-07-26
  - id: scenario-canonicalization-directive-2026-08-02
    resource: /sources/scenario-canonicalization-directive-2026-08-02.md
    title: PROVE leader Scenario canonicalization and traceability directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Required Chain

PROVE must preserve a navigable chain:

```text
Verification Request and version
→ Agent Workflow Run and Attempt lineage
→ Source document and version
→ Requirement or policy statement
→ Source Scenario Candidate
→ Canonical Scenario or Scenario Variant
→ generated Test Case version
→ build and validation evidence
→ execution configuration
→ Test Execution Run and retry lineage
→ DUT, FW, platform, and environment versions
→ raw and interpreted evidence
→ Test Verdict
→ Failure Analysis Record when failed
→ Failure Disposition and follow-up action
```

This chain must be navigable in both directions. It must support many-to-many relationships without discarding Source-specific meaning. Mapping, merge, split, variant, conflict, and supersession decisions must remain versioned and auditable.

No link may silently overwrite an earlier interpretation. An unresolved relationship remains explicitly unresolved until approved Evidence or human policy changes its state.

# AI Reproducibility

Record at least:

- Model and version
- Prompt or instruction version
- Agent workflow version
- Retrieved knowledge and source versions
- Tools and tool inputs
- Generated artifacts and diffs
- Execution system and dependency versions
- Analysis evidence and disposition

Reproducibility means complete audit reconstruction, replay where pinned dependencies remain available, and verification-result equivalence where generative output may differ. Exact byte identity is required only by explicit deterministic contracts; unavailable dependencies and substitutions must be visible.

# Change Rule

Generated modifications must create a new version. A Test Case must be revalidated before an official package adopts the modified version. A knowledge concept must not become `stable` solely because an agent generated it.

Test generation, execution, and Coverage evaluation remain versioned events or Evidence. Official Test adoption is demonstrated by an immutable Package or Gate Baseline Manifest reference to the exact validated Test Version.

Incorrect operational Knowledge with historical use is revoked rather than deleted or overwritten. Traceability must identify every affected downstream asset and claim, preserve the historical configuration, and connect it to correction, supersession, and revalidation results.

# Output Review Rule

Every durable stage Output must link to its exact Inputs, producing Run, validation Evidence, and versioned Review Record. An accepted or explicitly conditionally accepted Output becomes the downstream Input; a revised Output receives a new Version. Raw events and Evidence retain integrity and completeness checks even when semantic acceptance is not applicable.

# Retention

Long-term storage of prompts, responses, generated code, and logs is permitted. Retention and deletion policy remains a TF decision.
