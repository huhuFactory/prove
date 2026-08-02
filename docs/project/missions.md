---
type: Project Model
title: PROVE Two Mission Model
description: Current working model of the two PROVE input paths and their shared verification pipeline.
tags: [prove, missions, spec, flair, traceability]
status: draft
sources:
  - id: discovery-2026-08-02
    resource: /sources/discovery-2026-08-02.md
    title: PROVE working discovery discussion
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Current Working Model

PROVE has two primary input paths that converge on one shared verification pipeline. This model is a draft and may change as the TF refines its plan.

# Mission 1: Test Specification to Executable Verification

```text
Test Specification
→ Requirement extraction
→ Test Scenario derivation
→ executable Test generation
→ execution in a real SSD environment
→ Test validity and result analysis
```

The required traceability chain spans the source specification and version, extracted Requirement, derived Scenario, generated Test, execution context, evidence, and result.

# Mission 2: FLAIR-Integrated Firmware Verification

FLAIR develops SSD firmware through AI Agents and Vibe Coding. PROVE consumes relevant FLAIR development context, such as firmware policy, specifications, requirements, source context, change intent, and generated or modified code.

```text
FLAIR development context
→ Requirement and change-impact extraction
→ shared PROVE Scenario and Test pipeline
→ execution in a real SSD environment
→ verification feedback
```

The exact FLAIR input and output contracts are not yet defined.

# Shared Core

The two missions must not create separate downstream verification products. After input normalization, they share Requirement modeling, Scenario derivation, Coverage evaluation, Test generation, execution, failure disposition, and Traceability.

# Terminology Status

The conceptual distinction is agreed: a Test Case is the concrete verification selection, while a Test Script is its replaceable executable implementation. Whether they share one physical artifact, and their exact schema and file representation, cannot yet be decided.
