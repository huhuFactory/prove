---
type: Principle
title: PROVE Core Value
description: Non-negotiable project goal centered on verification knowledge and measurable Coverage.
tags: [prove, core, coverage, verification-knowledge]
status: stable
sources:
  - id: core-directive-2026-07-27
    resource: /sources/coverage-core-directive-2026-07-27.md
    title: PROVE leader Coverage core directive
    author: human:prove-leader
    last_modified: 2026-07-27
generated: { by: openai-codex/gpt-5, at: "2026-07-27T00:00:00+09:00" }
verified: { by: "human:prove-leader", at: "2026-07-27T00:00:00+09:00" }
---

# Core Statement

PROVE's core is not the ability to generate Test Case code. Its core is to structure accumulated SSD verification knowledge, use that knowledge to create better and broader tests, and provide defensible evidence of what the resulting tests cover.

```text
Existing Test Cases and engineering experience
→ explicit Verification Knowledge
→ AI-generated Test Scenarios and Test Cases
→ measurable preservation, loss, and expansion of verification capability
```

# Two Independent Obligations

A replacement or integrated Test Package must address both obligations independently:

1. **Verification Intent Preservation**

   Preserve what experienced Test engineers intended to verify, including knowledge that is implicit in existing Test Cases rather than written in a specification.

2. **Defect-Detection Capability Preservation**

   Demonstrate that the new package can detect the SSD failures that the existing package could detect.

Neither Test Case count, code similarity, nor semantic similarity alone proves equivalence. One generated Test Case may consolidate several legacy intentions, while many legacy Test Cases may duplicate one intention.

# Central Unsolved Problem

Coverage cannot be claimed as an absolute percentage until PROVE defines the verification space that represents 100%. Defining that space, its boundaries, and a defensible measurement method is a primary TF problem.

PROVE currently has no approved answer. The absence of an answer must remain visible rather than being hidden behind an early metric.

# Deliberate Deferral of Coverage Axes

The specific Coverage axes are intentionally not defined at this time. PROVE verification experts will refine and approve them through TF discussion and evidence.

Agents and subprojects may propose candidate dimensions or experiments, but must label them as hypotheses. They must not turn a candidate into a Root standard, aggregate score, or success claim without an approved decision.

# Role of Existing Tests

Existing Test Cases are not only migration inputs. They are evidence of accumulated engineering knowledge. PROVE must extract reusable verification intent and patterns from them so that a new specification can receive expert-level tests even when the specification does not state that experience explicitly.

# Tool Neutrality

IceT, SkyTower, implementation languages, models, RAG systems, and agent frameworks are enabling tools. They may be redesigned, adapted, or replaced.

Technology choices are evaluated by how effectively they support:

- Verification knowledge extraction and reuse
- Better and broader Test Case generation
- Coverage measurement
- Execution evidence and reproducibility
- Verification-intent and defect-detection comparison

No tool is allowed to become the project goal.

# Rule for Every Participant and Agent

Before proposing or implementing work, state how it contributes to this core. If a tool-specific optimization conflicts with verification knowledge, Coverage evidence, or long-term extensibility, the core value takes precedence.
