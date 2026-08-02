---
type: Architecture
title: PROVE System Context
description: High-level systems, actors, inputs, and outputs surrounding PROVE.
tags: [prove, architecture, context]
status: draft
sources:
  - id: discovery-2026-07-26
    resource: /sources/discovery-interview-2026-07-26.md
    title: PROVE leader discovery discussion
    author: human:prove-leader
    last_modified: 2026-07-26
  - id: core-directive-2026-07-27
    resource: /sources/coverage-core-directive-2026-07-27.md
    title: PROVE leader Coverage core directive
    author: human:prove-leader
    last_modified: 2026-07-27
  - id: discovery-2026-08-02
    resource: /sources/discovery-2026-08-02.md
    title: PROVE working discovery discussion
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Context

```mermaid
flowchart LR
    Requester["Engineer / Team / Approved Upstream Requester"] --> Request["User Verification Request"]
    Request --> Core
    Specs["NVMe / OCP / Customer / Internal Specs"] --> Core["Verification Knowledge and Coverage Core"]
    RAG["Internal Spec RAG"] --> Core
    Packages["Existing Test Packages"] --> Core
    FLAIR["FLAIR FW Policy / Spec / Code Context"] --> Core

    Core --> PROVE["PROVE Agent Workflow"]
    PROVE --> IceT["IceT — Enabling Test Tool"]
    PROVE --> SkyTower["SkyTower — Enabling Automation Tool"]
    IceT --> DUT["eSSD / cSSD DUT"]
    SkyTower --> IceT

    DUT --> Evidence["Logs and Execution Evidence"]
    IceT --> Evidence
    SkyTower --> Evidence
    Evidence --> PROVE

    PROVE --> Package["Validated Test Package"]
    PROVE --> BRAIN["BRAIN Failure Analysis"]
    BRAIN --> PROVE
    PROVE --> Human["Verification Engineer Escalation"]
```

# Architectural Priority

The Verification Knowledge and Coverage core defines what the surrounding tools must support. IceT and SkyTower are replaceable adapters and execution capabilities; their current architecture must not define the limits of PROVE.

# Inputs

- User or upstream-system Verification Request and execution constraints
- Official NVMe specifications
- OCP specifications
- Customer specifications
- Internal requirements and verification knowledge
- Existing test packages
- SRS, firmware policy, generated code, and code changes
- Historical SkyTower execution and failure data

# Outputs

- Requirements and Test Scenarios
- Executable Test Cases and configurations
- Expected results and traceability
- Coverage and quality evidence
- Execution records
- Device/non-device/unknown dispositions
- Reproduction and analysis reports
- Validated package changes
- Human intervention requests

# Unresolved Interfaces

Detailed SkyTower structure, FLAIR and BRAIN contracts, Spec RAG mutation rights, and repository boundaries remain open.
