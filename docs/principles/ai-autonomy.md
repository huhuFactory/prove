---
type: Principle
title: AI Autonomy Principles
description: Intended autonomous behavior and escalation boundaries for PROVE agents.
tags: [prove, ai, autonomy, failure-analysis]
status: draft
sources:
  - id: discovery-2026-07-26
    resource: /sources/discovery-interview-2026-07-26.md
    title: PROVE leader discovery discussion
    author: human:prove-leader
    last_modified: 2026-07-26
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Intended Autonomy

PROVE targets an end-to-end workflow without routine human approval:

- Extract scenarios.
- Generate code, configuration, expected results, and traceability.
- Build and validate Test Cases.
- Execute on real SSDs.
- Analyze and reproduce failures.
- Register device failures in a downstream system.
- Repair Test Case failures.
- Recover environmental failures.
- Revalidate and rerun.
- Promote validated Test Cases to an official package.
- Request human intervention when automation cannot proceed.

# Guardrail Model

Guardrails must preserve test intent rather than ban adverse device operations. They should focus on:

- Platform control and liveness
- Bounded retry and repair loops
- Complete evidence capture
- Versioned changes
- Deterministic escalation
- Reproducible model, prompt, tool, code, and environment history
- Immutable first-Failure Evidence before Reset, recovery, rerun, or repair

# Human Escalation

`Unknown`, unrecoverable environment states, exhausted repair limits, and policy-required decisions may trigger human intervention. Confidence thresholds and responsibility assignments are not yet defined.

# Feedback

A device failure handed to a downstream system remains a PROVE disposition. If downstream analysis reclassifies it as non-device, that result must return to PROVE for reanalysis and future evaluation.

# Draft Knowledge Boundary

Agents may use Draft Verification Knowledge in an explicitly experimental lineage and collect promotion Evidence. Draft Knowledge must not silently influence official Coverage, project verdicts, official Test Packages, or Gate Baselines.
