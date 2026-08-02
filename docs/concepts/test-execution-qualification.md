---
type: Concept Model
title: Test Execution Qualification
description: Working qualification model separating generated Test quality from the IceT Platform control invariant.
tags: [prove, test, execution, quality, icet, evidence]
status: draft
sources:
  - id: test-execution-qualification-directive-2026-08-02
    resource: /sources/test-execution-qualification-directive-2026-08-02.md
    title: PROVE leader Test execution qualification directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Purpose

Generated Test quality cannot be established through document or code review alone. PROVE must distinguish what is being evaluated so a Platform Failure is not confused with a Test defect and a buildable Test is not mistaken for a meaningful one.

# Test Qualification Areas

| Area | Core question | Representative Evidence |
|---|---|---|
| Executable qualification | Can the Test be built and use the supported execution contract correctly? | Syntax, build, linkage, and API validation |
| Scenario-intent fidelity | Does the Test implement the conditions, state flow, and Verification Intent of its Scenario and Case? | Traceable steps, state observations, and intent comparison |
| Verdict capability | Can its Oracle distinguish the expected and relevant unexpected behavior with sufficient Evidence? | Expected/Actual comparison and verdict rationale |
| Operational reliability | Can it run on real Hardware with repeatable behavior and controlled cleanup or preserved state? | Hardware runs, timeout, crash, Flaky, cleanup, recovery, and repetition records |

These areas remain separately visible. The acceptance thresholds and repetition policy are not yet defined.

# IceT Platform Invariant

For every technically supported verification action, including Reset, injected Error, and abnormal Device state, IceT must retain control of execution and Evidence. It must continue, recover, or terminate deterministically rather than stop unexpectedly.

This is a cross-cutting Platform qualification, not another property of an individual Test. A run observes both the Test and Platform, but classifies their results separately:

```text
Correct Test + qualified IceT execution
→ usable execution Evidence

Correct or still-unknown Test + IceT loses control
→ Platform Failure candidate
→ execution result is insufficient for Test promotion
→ recover, rerun, and preserve both attempts
```

# Relationship to Lifecycle

Static success alone does not make a Test official. Real execution Evidence, Scenario-intent Evidence, verdict Evidence, and operational Evidence feed [Test Version and Official Adoption](/concepts/test-version-and-official-adoption.md). The minimum Evidence and authority required for `Validated` cannot yet be decided.

# Execution Candidate Selection

The Test Cases selected for execution are not one fixed enterprise-wide list. Each verification team selects candidates for its R&R, product scope, verification purpose, time budget, Hardware, and Tool constraints. Common qualification areas still apply to the selected Cases, and every inclusion or exclusion must remain traceable. Technical environment matching is addressed by the separate Applicability model.
