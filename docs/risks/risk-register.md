---
type: Risk Register
title: PROVE Initial Risk Register
description: Known risks discovered during initial project framing.
tags: [prove, risks, planning]
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

# Risks

| ID | Risk | Current response |
|---|---|---|
| R-001 | Coverage is central but the verification space and axes are undefined, so early percentages may create false confidence. | Keep all values experimental until verification experts approve the space, axes, evidence, and attested computation. |
| R-002 | Simultaneous IceT redesign, language change, agent workflow, execution, and analysis create coupling. | Define capability and interface boundaries before assigning repository implementation. |
| R-003 | IceT lacks the planned C++ runtime, API guide, examples, and coding rules. | Treat the execution contract and verification specification as explicit deliverables. |
| R-004 | Historical SkyTower data is large and stored without connected analysis lineage. | Start with a curated evaluation slice; design stable identifiers and extraction separately. |
| R-005 | SkyTower APIs exist but are too heavy for the intended workflow. | Define a PROVE-facing contract without assuming the current API is the long-term boundary. |
| R-006 | One backend expert is expected to cover SkyTower adaptation and agent infrastructure. | Confirm ownership, dependencies, and support after work decomposition. |
| R-007 | Autonomous Test Case repair and package promotion may propagate incorrect changes. | Require versioning, automated revalidation, evidence, rollback, and bounded loops. |
| R-008 | Device/non-device misclassification can waste analysis or miss SSD defects. | Define confidence, unknown handling, feedback, and evaluation thresholds. |
| R-009 | Customer specifications may not be allowed in commercial LLM requests. | Enforce source-level data policy and retain an approved alternative path. |
| R-010 | Root and subproject knowledge may drift across repositories. | Pin Root versions, review upgrades, and automate conformance and link checks. |
| R-011 | Execution systems for each TF engineer are expected but not yet requested. | Track resource confirmation as an explicit dependency. |
| R-012 | Project duration and workstream ownership remain flexible. | Use evidence-based stage exits and assign accountable owners through TF review. |
| R-013 | IceT, SkyTower, or another tool may become a de facto project goal and constrain the verification model. | Require every subproject decision to trace to the stable Core Value and keep tool boundaries replaceable. |

# Scoring

Likelihood, impact, owner, due date, and residual risk are not yet assessed. The TF should add them after reviewing scope and dependencies.
