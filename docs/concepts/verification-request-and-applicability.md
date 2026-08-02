---
type: Concept Model
title: Verification Request and Applicability
description: Working model for translating a user's verification intent into traceable Test selection and a feasible real-environment execution plan.
tags: [prove, verification-request, applicability, environment, execution]
status: draft
sources:
  - id: verification-request-applicability-directive-2026-08-02
    resource: /sources/verification-request-applicability-directive-2026-08-02.md
    title: Verification Request Applicability directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Definition

Applicability is PROVE's ability to transform a user's verification Requirements into executable Tests and a feasible real-environment plan without losing the original intent or silently replacing an unmet condition.

User input may be expressed through natural language, Specifications, configuration, or an approved upstream system. Before generation and execution, PROVE normalizes that input into a versioned **Verification Request**. This is the top-level Traceability unit for the resulting verification work.

```text
User Verification Request
→ applicable Source and Requirement context
→ Scenario and Test Case selection
→ Test execution constraints
→ available environment capabilities
→ Execution Plan or explicit unmet condition
```

The requester may be a verification engineer, a team workflow, FLAIR, or another approved upstream system. The request format and mandatory fields remain open.

# Two Related Decisions

1. **What to verify** is resolved from the user's purpose, project, Main/Deri, product, customer and Specification obligations, team R&R, time budget, and requested verification scope.
2. **Where and how to execute** is resolved from the selected Cases, their preconditions and required capabilities, the requested constraints, and the environments actually available.

These decisions must remain connected. An execution Agent does not choose an environment from Test metadata alone or according to its own preference.

# Resolution Rules

- Link every derived Requirement, Scenario, Case, Execution Plan, run, Evidence item, and verdict to the originating Verification Request version.
- Preserve requested, derived, defaulted, and unresolved information as distinguishable states.
- Do not silently substitute another product, Specification version, Hardware, or reduced scope when a request cannot be satisfied.
- A user may explicitly require a named Hardware or environment; otherwise PROVE may resolve a compatible environment from declared capabilities.
- Record why every Scenario, Case, and environment was included, excluded, or left unresolved.
- Return an explicit Gap or unmet-condition result when no valid plan exists.
- Preserve the exact Request, selected assets, environment, Baseline, and Agent decision Evidence in Traceability.

# Boundary

The detailed request schema, input UI, Capability taxonomy, selection algorithm, scheduling policy, and user interaction belong to later design with verification-team experts. Applicability determines validity and feasibility; it does not by itself define Coverage or override each team's Test selection authority.
