---
type: Metric Framework
title: Test Quality and Coverage
description: Authoritative problem statement and decision boundary for future Coverage definition.
tags: [prove, coverage, quality, evaluation]
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

# Status

Coverage is the central PROVE research and engineering problem. No authoritative verification space, Coverage axis, aggregate score, or computation is approved.

# Authoritative Position

- A claim such as "100% Coverage" has no meaning until its verification space is defined.
- Coverage is not inferred from Test Case count, code similarity, or generation success.
- Global package equivalence requires separate evaluation of:
  - Verification Intent preservation;
  - actual defect-detection capability preservation.
- Existing Test Cases are sources of implicit expert knowledge, not only code to translate.
- Specific Coverage axes are intentionally deferred to PROVE verification experts.

# Central Questions

1. What constitutes the verification space?
2. How are its boundaries made explicit and reviewable?
3. How is implicit engineering intent extracted from existing Test Cases?
4. How is Intent preservation distinguished from defect-detection preservation?
5. How are loss, redundancy, and valid expansion demonstrated?
6. What static and dynamic evidence makes a Coverage claim defensible?
7. How is knowledge from legacy tests applied to a new specification?

# Deliberate Non-Definition

This document does not define Coverage axes. Candidate axes, weights, formulas, and composite scores must remain experimental until reviewed by the TF's verification experts and accepted through an ADR.

# Comparison Model

Conceptually, PROVE must compare:

```text
Legacy Test Package
→ extracted Verification Intent and engineering knowledge
→ comparison with generated Test Package
→ preserved, lost, redundant, and newly added verification capability
```

Semantic comparison alone is insufficient for equivalence. The future evaluation method must consider both structured intent and execution-based defect-detection evidence. The exact evidence protocol is not yet approved.

# Knowledge Reuse

PROVE must derive reusable Verification Knowledge from legacy Test Cases and engineering experience. That knowledge must inform Test Scenario generation for new specifications so generated tests are not limited to requirements explicitly written in the new document.

# Required Foundation Work

- Verification-expert workshops to define the space-construction method
- A canonical representation for Verification Intent
- Traceable extraction from existing Test Cases
- Representative legacy and generated packages for comparison
- Historical or controlled defect evidence where available
- A method for recording uncertainty and unmatched knowledge

The detailed axes, dataset size, and acceptance thresholds remain open.

# Reporting Rule

When a Coverage computation becomes authoritative, define it as an OKF `Attested Computation` with a deterministic executor, receipt, and attester. Until then, reported Coverage values must be labeled experimental.
