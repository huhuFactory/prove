---
type: Architecture Proposal
title: Verification Pattern and Unified Test Library
description: Proposed separation of semantic verification knowledge from executable library implementations.
tags: [prove, verification-pattern, test-library, test-scenario]
status: draft
sources:
  - id: scenario-primacy-2026-08-02
    resource: /sources/scenario-primacy-directive-2026-08-02.md
    title: PROVE leader Test Scenario primacy directive
    author: human:prove-leader
    last_modified: 2026-08-02
  - id: iso-keyword-testing
    resource: https://www.iso.org/standard/87233.html
    title: ISO/IEC/IEEE 29119-5:2024 Keyword-Driven Testing
    author: team:iso-jtc1-sc7
    last_modified: 2024-12-01
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Recommendation

Do not embed all reusable engineering knowledge only inside Test Scenarios, and do not make Test Library code the sole representation of that knowledge.

Use three distinct but linked assets:

```text
Verification Pattern
→ applied within a Test Scenario
→ implemented by one or more Test Library capabilities
```

# Verification Pattern

An implementation-independent description of reusable expert knowledge:

- Intent and failure risk
- Applicability and exclusions
- Required preconditions
- Stimulus or intervention concept
- Invariants and expected observations
- Required Evidence
- Known historical context

Example: interrupt a state-changing operation at a meaningful phase, recover the device, and verify externally observable consistency.

# Test Scenario

The primary asset that applies Requirements and Patterns to a specific verification objective and logical flow. Scenario remains the authoritative unit for Traceability and Coverage reasoning.

# Unified Test Library

The executable realization of reusable capabilities, such as reset, power control, recovery, data validation, or command composition. A Pattern may have multiple Library implementations for different IceT versions or hardware capabilities.

# Why the Separation Matters

- Library code explains how, but often obscures why and when.
- Scenario-only knowledge creates repetition and weak reuse.
- Pattern-only design can become abstract unless connected to executable Library capabilities.
- Separating semantics from implementation allows regeneration when languages, IceT, or hardware change.

# Proposed Governance

- Pattern changes require knowledge review.
- Scenario changes require Coverage and Traceability impact review.
- Library changes require implementation and execution validation.
- Links among Pattern, Scenario, Test Case, Script, and Evidence remain versioned.

# Decision Needed

The TF must decide Pattern granularity, ownership, approval, and how unified Library capabilities declare which Patterns they implement.
