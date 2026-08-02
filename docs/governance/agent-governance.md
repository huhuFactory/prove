---
type: Governance
title: PROVE Agent Governance
description: Rules for agents that consume, generate, execute, analyze, or maintain PROVE knowledge.
tags: [prove, agents, governance, safety]
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

# Core Alignment

Every Agent must read [PROVE Core Value](/principles/core-value.md) before project-local knowledge. It must explain how a proposal contributes to Verification Knowledge, better or broader tests, measurable Coverage, or evidence.

Agents must not:

- Treat IceT, SkyTower, a language, a model, or an agent framework as the project goal.
- Define a Coverage axis, formula, weight, or aggregate score as authoritative.
- Claim package equivalence from Test Case count, code similarity, or semantic similarity alone.
- Collapse Intent preservation and defect-detection preservation into one unexamined metric.

# Grounding

Agents must load the pinned Root Knowledge and relevant local knowledge before acting. They must distinguish confirmed facts, accepted decisions, proposals, hypotheses, and unknowns.

# Provenance

Agents must preserve source versions and link generated claims to evidence. Summaries must not erase conflicts or exceptions present in source material.

# Execution

Test agents may perform adverse device operations required by test intent. They must preserve platform control, evidence collection, bounded loops, and deterministic escalation.

# Change Control

- Generated code and documents are versioned.
- Test repairs are validated before official-package promotion.
- Root policy changes require Root review.
- Agents must not claim human verification.
- Automatic actions must be attributable to a model, workflow, tool, and input version.

# Artifact Input, Output, and Review

Every Agent stage declares its exact versioned Inputs and produces a versioned Output. Each durable Output links to its producing Run and receives an artifact-appropriate Review Record before official downstream use. Accepted Outputs become downstream Inputs; revision creates a new Version. Raw events and Evidence receive integrity and completeness checks when semantic acceptance is not applicable.

An Agent must explicitly state when a schema, threshold, authority, or policy cannot yet be decided. It must not fill that gap through an undocumented default.

# Failure Handling

Agents classify failures as device, non-device, or unknown. Non-device failures receive type-specific analysis, repair or recovery, validation, and rerun. Unknown or exhausted cases request human intervention with collected evidence.

# Knowledge Promotion Boundary

An Agent may create Draft Knowledge, collect Evidence, and recommend promotion. The Knowledge-producing Agent must not independently promote its own output to official Trust. Initial promotion uses independent evaluation and approval by the accountable expert for the target scope.

# Run Identity

Every Agent workflow attempt has an immutable Run identity linked to its Verification Request. Retry, resume, regeneration, Model or Prompt changes, and re-execution create linked new Attempts rather than overwriting prior events or artifacts.

Agent Handoffs reference versioned Artifacts and Evidence. Resume may use only a still-valid Checkpoint; changed upstream inputs invalidate the affected downstream work. Retry must be bounded and traceable even when its exact policy is project-specific.

# Security

Commercial LLM use is approved for internal specifications, Test Cases, logs, and firmware material. Customer-specification transmission remains conditional on NDA review. Agents must enforce the effective policy at input time rather than relying on document accessibility alone.

# Framework Independence

No specific framework, including LangGraph, is mandatory. Agent roles and workflow contracts must be portable.
