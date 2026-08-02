---
type: Concept Model
title: Test Design, Scenario, Case, and Script
description: Standards-informed working terminology for PROVE Test artifacts and activities.
tags: [prove, terminology, test-design, test-scenario, test-case, test-script]
status: draft
sources:
  - id: istqb-test-analyst
    resource: https://www.istqb.org/wp-content/uploads/2024/11/ISTQB_CTAL-TA_Syllabus_v3.1.2.pdf
    title: ISTQB Certified Tester Advanced Level Test Analyst Syllabus
    author: team:istqb
    last_modified: 2024-11-01
  - id: iso-29119-series
    resource: https://committee.iso.org/sites/jtc1sc7/home/projects/flagship-standards/isoiecieee-29119-series.html
    title: ISO/IEC/IEEE 29119 Software Testing Series
    author: team:iso-jtc1-sc7
  - id: scenario-case-directive-2026-08-02
    resource: /sources/scenario-case-generation-directive-2026-08-02.md
    title: PROVE leader Scenario and Case generation directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Standards Context

ISO/IEC/IEEE 29119 separates test processes, documentation, design techniques, and implementation. ISTQB similarly distinguishes Test Analysis, Test Design, Test Implementation, and Test Execution. PROVE should preserve these distinctions while defining `Test Scenario` explicitly for its own domain.

# Test Design

Test Design is an activity, not primarily an executable artifact. It refines identified test conditions using test techniques and determines objectives, preconditions, data, expected results, postconditions, environments, and traceability.

PROVE use: the process that transforms Requirements, Coverage needs, Verification Patterns, and risk into Test Scenarios and Test Cases.

# Test Scenario

Test Scenario is PROVE's high-level, implementation-independent verification asset. It states:

- What behavior or risk is verified
- Why the verification is needed
- Applicable Requirement and knowledge
- Preconditions and relevant context
- Intended stimulus and logical flow
- Expected invariant or observable outcome
- Required Evidence categories

It does not bind all concrete values or prescribe one Test Library implementation.

In the PROVE model, Scenario defines the meaningful verification intent and space that Test Cases must fill.

# Test Case

Test Case is a concrete, repeatable, and verifiable specification derived from a Scenario. It binds sufficient execution detail, including:

- Objective and Scenario reference
- Preconditions and environment constraints
- Concrete or parameterized Test data
- Actions and sequencing
- Expected results and pass/fail criteria
- Postconditions, cleanup, or recovery
- Required Evidence

A Scenario may produce multiple Test Cases for parameters, environments, products, or techniques.

Test Case is not merely a generated row in a Cartesian product. A useful Case selects a meaningful state, path, boundary, interaction, risk, or exploratory point and remains traceable to why that selection matters.

# Test Script

Test Script is the executable automation implementation of a Test Case for a specific runtime and API contract. In PROVE this may include generated code, configuration, dependency declarations, and references to unified Test Library functions.

A Test Case should remain meaningful when its Script is regenerated in a new language or runtime.

# Proposed Relationship

```text
Requirement and Verification Pattern
→ Test Design activity
→ Test Scenario
→ one or more Test Cases
→ one or more executable Test Scripts
→ Execution and Evidence
```

# Decision Status

The TF leader has confirmed Scenario primacy, Test Case generation as a core capability, and Test Script replaceability. The complete schemas, granularity, and lifecycle remain proposals requiring TF review.
