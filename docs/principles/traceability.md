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
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Required Chain

PROVE must preserve a navigable chain:

```text
Source document and version
→ Requirement or policy statement
→ Test Scenario
→ generated Test Case version
→ build and validation evidence
→ execution configuration
→ DUT, FW, platform, and environment versions
→ raw and interpreted evidence
→ verdict and follow-up action
```

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

# Change Rule

Generated modifications must create a new version. A Test Case must be revalidated before an official package adopts the modified version. A knowledge concept must not become `stable` solely because an agent generated it.

# Retention

Long-term storage of prompts, responses, generated code, and logs is permitted. Retention and deletion policy remains a TF decision.
