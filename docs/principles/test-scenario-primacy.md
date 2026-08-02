---
type: Principle
title: Test Scenario Primacy
description: Stable rule that Test Scenario is PROVE's most important long-term verification asset.
tags: [prove, test-scenario, core, verification-knowledge]
status: stable
sources:
  - id: scenario-primacy-2026-08-02
    resource: /sources/scenario-primacy-directive-2026-08-02.md
    title: PROVE leader Test Scenario primacy directive
    author: human:prove-leader
    last_modified: 2026-08-02
  - id: scenario-case-directive-2026-08-02
    resource: /sources/scenario-case-generation-directive-2026-08-02.md
    title: PROVE leader Scenario and Case generation directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
verified: { by: "human:prove-leader", at: "2026-08-02T00:00:00+09:00" }
---

# Principle

Test Scenario is PROVE's most important long-term asset. Extracting and generating high-quality Test Scenarios is a core project capability, not an intermediate documentation task.

# Why Scenario Is Primary

A Test Scenario preserves what must be verified, why it matters, and under which conditions and flow it applies. It should remain useful when Test code, Test Library, IceT implementation, hardware, language, model, or Agent framework changes.

Scenario primacy does not make Test Case generation secondary to PROVE's mission. Scenario defines meaningful verification intent and the space to be explored; Test Cases select concrete states, paths, conditions, and parameter combinations that fill that space. Test Script is the replaceable executable implementation of a Case.

# Required Traceability

```text
Source and Requirement
→ Test Scenario
→ Test Case
→ Test Script
→ execution and Evidence
→ Coverage claim and Gap
→ result and Failure disposition
```

# Consequences

- Legacy migration prioritizes reliable Scenario extraction before Test regeneration.
- Scenario quality requires explicit evaluation.
- Generating, selecting, and evaluating Coverage-meaningful Test Cases is a core capability.
- Generated Test correctness is judged against Scenario intent and flow.
- Test Script language and runtime may change without changing Scenario or Case meaning.
- Reusable Verification Patterns may support many Scenarios but do not replace them.
- Test Libraries implement reusable behavior but are not the authoritative semantic form of Scenario knowledge.
