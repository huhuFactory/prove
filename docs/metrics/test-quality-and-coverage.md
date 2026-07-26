---
type: Metric Framework
title: Test Quality and Coverage
description: Current problem statement and hypotheses for evaluating AI-generated SSD tests.
tags: [prove, coverage, quality, evaluation]
status: draft
sources:
  - id: discovery-2026-07-26
    resource: /sources/discovery-interview-2026-07-26.md
    title: PROVE leader discovery discussion
    author: human:prove-leader
    last_modified: 2026-07-26
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Status

Coverage is a central PROVE research and engineering problem. No authoritative Coverage definition or computation is approved yet.

# Core Questions

1. What is the finite or measurable verification space?
2. Which dimensions represent meaningful SSD behavior?
3. How is a Test Scenario mapped into that space?
4. How are overlap, redundancy, gaps, and depth measured?
5. How is semantic correctness separated from numerical Coverage?
6. How does evidence prove that generated tests are useful?

# Candidate Dimensions

The following are hypotheses for TF evaluation, not accepted definitions:

- Specification requirement coverage
- Command and feature coverage
- State and state-transition coverage
- Parameter and boundary-value coverage
- Error and negative-path coverage
- Reset, power, and recovery coverage
- Cross-feature interaction coverage
- Environment and configuration coverage
- Expected-result and assertion coverage
- Historical failure coverage
- Code coverage where source access and interpretation are meaningful

# Test Quality Dimensions

Coverage alone is insufficient. Candidate quality evidence includes:

- Requirement fidelity
- Scenario correctness
- Executability
- Determinism and reproducibility
- Strength of expected results
- Failure-detection ability
- Traceability
- Maintainability
- Novelty versus existing tests
- Expert correction effort

# Required Evaluation Assets

- Versioned source requirements
- Expert-authored scenarios and tests
- Existing representative Test Cases
- Known device and non-device failure examples
- A reviewed mapping between requirements, scenarios, tests, and expected evidence

The size and availability of a representative failure dataset are open.

# Governance

When a Coverage computation becomes authoritative, define it as an OKF `Attested Computation` with a deterministic executor, receipt, and attester. Until then, reported Coverage values must be labeled experimental.
