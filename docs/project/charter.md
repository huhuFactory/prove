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
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Mandate

Establish the goals, knowledge, evaluation method, and technical foundation for an AI-native SSD verification platform.

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

- A defensible definition and measurement method for Test Case quality and Coverage
- An AI-native IceT direction and executable test contract
- Agent workflow integration from knowledge input through execution and analysis
- A reproducible failure-analysis loop
- A durable Root Knowledge system shared by all PROVE subprojects
