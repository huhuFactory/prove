---
type: Architecture
title: FLAIR–PROVE–BRAIN Workflow
description: Current working responsibility and automation boundaries among firmware development, verification, and failure analysis.
tags: [prove, flair, brain, failure-analysis, closed-loop]
status: draft
sources:
  - id: discovery-2026-08-02
    resource: /sources/discovery-2026-08-02.md
    title: PROVE working discovery discussion
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Responsibilities

- **FLAIR**: AI Agent and Vibe Coding-based SSD firmware development.
- **PROVE**: Requirement and Scenario extraction, Test generation and execution, official Pass/Fail decision, and device/non-device Failure disposition.
- **BRAIN**: AI Agent-based detailed analysis of SSD firmware failures.

Within PROVE, a Test Fail triggers the PROVE Failure Analysis Agent. This Agent determines Device, Non-device, or Unknown Disposition. It is distinct from BRAIN, which receives a Device Failure after that PROVE decision.

# Failure Flow

```mermaid
flowchart LR
    FLAIR["FLAIR firmware development"] --> PROVE["PROVE generation and execution"]
    PROVE --> FA["PROVE Failure Analysis Agent"]
    FA --> D{"Failure disposition"}
    D -->|Non-device| Repair["PROVE repair or recovery and rerun"]
    Repair --> PROVE
    D -->|Device| BRAIN["BRAIN AI analysis"]
    BRAIN --> Feedback["Analysis and classification feedback"]
    Feedback --> PROVE
    Feedback -. future .-> FLAIR
```

# Automation Position

In the current target, a PROVE device-failure disposition is handed to BRAIN automatically without human approval, and BRAIN Agents begin analysis automatically.

PROVE does not need to prove the internal SSD root cause before this handoff. A defined Device-behavior violation supported by direct Evidence or reasonable exclusion of Non-device causes is sufficient under the future approved Evidence policy.

If BRAIN reclassifies the Failure as non-device, the result returns to PROVE for reanalysis and improvement.

# Long-Term Closed Loop

The desired future loop sends BRAIN root-cause analysis to FLAIR, lets FLAIR modify firmware, and invokes PROVE for regeneration or regression execution until an exit condition is reached. This complete loop is a target, but not part of the committed first two-month outcome.

# Open Contracts

FLAIR development-context schema, PROVE-to-BRAIN handoff schema, BRAIN feedback schema, loop limits, and final authority remain to be defined.
