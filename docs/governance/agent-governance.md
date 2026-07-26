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
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

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

# Failure Handling

Agents classify failures as device, non-device, or unknown. Non-device failures receive type-specific analysis, repair or recovery, validation, and rerun. Unknown or exhausted cases request human intervention with collected evidence.

# Security

Commercial LLM use is approved for internal specifications, Test Cases, logs, and firmware material. Customer-specification transmission remains conditional on NDA review. Agents must enforce the effective policy at input time rather than relying on document accessibility alone.

# Framework Independence

No specific framework, including LangGraph, is mandatory. Agent roles and workflow contracts must be portable.
