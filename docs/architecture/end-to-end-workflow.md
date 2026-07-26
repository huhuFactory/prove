---
type: Architecture
title: PROVE End-to-End Workflow
description: Target autonomous lifecycle from knowledge input through verdict and repair.
tags: [prove, workflow, agents, execution]
status: draft
sources:
  - id: discovery-2026-07-26
    resource: /sources/discovery-interview-2026-07-26.md
    title: PROVE leader discovery discussion
    author: human:prove-leader
    last_modified: 2026-07-26
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Target Workflow

```mermaid
flowchart TD
    A["Select versioned source knowledge"] --> B["Extract requirements and scenarios"]
    B --> C["Generate Test Case, configuration, expected result, and traceability"]
    C --> D["Build and automated validation"]
    D -->|Invalid| C
    D -->|Valid| E["Execute through IceT and execution infrastructure"]
    E --> F["Collect device, platform, host, environment, and FW evidence"]
    F --> G["Reproduce and analyze"]
    G --> H{"Disposition"}
    H -->|Device failure| I["Send evidence to downstream failure system"]
    I --> J{"Downstream correction?"}
    J -->|Reclassified| G
    J -->|Confirmed| K["Close PROVE workflow"]
    H -->|Test Case issue| L["Generate versioned repair"]
    L --> D
    H -->|Environment issue| M["Recover environment"]
    M --> E
    H -->|Other non-device| N["Apply type-specific action"]
    N --> E
    H -->|Unknown or exhausted| O["Request human intervention with evidence"]
    E --> P["Update quality and Coverage evidence"]
```

# Loop Exit Conditions

- Pass
- Device failure transferred with evidence
- Repair or recovery limit exceeded
- Unknown disposition requiring a person
- Policy-mandated stop

# Framework Independence

LangGraph is an example, not a mandated framework. Workflow contracts must remain independent of a specific agent-orchestration product.

# Execution Topology

Engineering development should use systems compatible with the SkyTower execution model. Local and Mass environments should share workflow and execution contracts rather than becoming separate products.
