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
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Context

```mermaid
flowchart LR
    Specs["NVMe / OCP / Customer / Internal Specs"] --> PROVE["PROVE Agent Workflow"]
    RAG["Internal Spec RAG"] --> PROVE
    Packages["Existing Test Packages"] --> PROVE
    FW["SRS / FW Policy / Code"] --> PROVE

    PROVE --> IceT["IceT Test Platform"]
    PROVE --> SkyTower["SkyTower Automation"]
    IceT --> DUT["eSSD / cSSD DUT"]
    SkyTower --> IceT

    DUT --> Evidence["Logs and Execution Evidence"]
    IceT --> Evidence
    SkyTower --> Evidence
    Evidence --> PROVE

    PROVE --> Package["Validated Test Package"]
    PROVE --> Downstream["Downstream Failure System"]
    Downstream --> PROVE
    PROVE --> Human["Verification Engineer Escalation"]
```

# Inputs

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

Detailed SkyTower structure, downstream failure-system API, Spec RAG mutation rights, and repository boundaries remain open.
