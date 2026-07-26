---
type: Project Charter
title: PROVE Project Charter
description: Initial mandate, outcomes, constraints, and operating context for the PROVE TF.
tags: [prove, charter, tf]
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
generated: { by: openai-codex/gpt-5, at: "2026-07-27T00:00:00+09:00" }
---

# Mandate

Establish a measurable SSD Verification Knowledge system that preserves expert intent and defect-detection capability while enabling AI-native Test Case generation, execution, and analysis.

# Primary TF Problem

The TF must define what constitutes the verification space and how Test Coverage is measured within it. There is no approved answer yet. Specific Coverage axes remain intentionally undefined until verification experts refine and approve them.

# Initial Operating Window

- Planned start: 2026-07-30
- Initial reporting window: approximately two months
- Weekly progress reporting
- First internal end-to-end demonstration target: 2026-08-27
- Initial result target: around 2026-09-30
- Final TF duration: adjustable based on the approved plan and results

Dates are planning targets, not a finalized delivery commitment.

# Initial Demonstration Intent

Demonstrate a thin end-to-end path across no more than ten features:

```text
Spec input
→ Test Scenario extraction
→ executable Test Case generation
→ execution
→ quality and Coverage evaluation
```

One or two specification types may be used initially. Exact documents, versions, and features remain open.

# Team

The TF has eight members, targeting 80–90% effective allocation:

- Five SSD test experts
  - Four eSSD verification experts with more than ten years of experience
  - One cSSD verification engineer with approximately four years of experience
- Three platform specialists
  - SSD Test Platform expert and TF leader
  - AI expert with SSD testing and platform experience
  - Mass-validation automation and backend expert

Workstream ownership and documentation roles are not yet assigned.

# Expected Outcomes

- A defensible definition of the verification space and a measurement method for Test Case quality and Coverage
- Independent evidence for Verification Intent preservation and defect-detection capability preservation
- A reusable representation of knowledge embedded in existing Test Cases
- An AI-native IceT direction and executable test contract
- Agent workflow integration from knowledge input through execution and analysis
- A reproducible failure-analysis loop
- A durable Root Knowledge system shared by all PROVE subprojects

# Technology Position

IceT, SkyTower, implementation languages, models, and orchestration frameworks support the mandate but do not define it. They may change when a different design better serves the core goal.
