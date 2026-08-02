---
type: Principle Proposal
title: Semantic and State-Aware Test Case Generation
description: TF discussion proposal for generating Cases from verification meaning, SSD state, and execution feedback rather than unguided input enumeration alone.
tags: [prove, test-case, state-aware, semantics, feedback, generation]
status: draft
sources:
  - id: scenario-case-directive-2026-08-02
    resource: /sources/scenario-case-generation-directive-2026-08-02.md
    title: PROVE leader Scenario and Case generation directive
    author: human:prove-leader
    last_modified: 2026-08-02
  - id: metis-fast-2024
    resource: https://www.usenix.org/conference/fast24/presentation/liu-yifei
    title: "Metis: File System Model Checking via Versatile Input and State Exploration"
    author: team:usenix
    last_modified: 2024-02-01
  - id: ssd-state-aware-fuzzing-2025
    resource: https://arxiv.org/abs/2505.03062
    title: "Testing SSD Firmware with State Data-Aware Fuzzing"
    author: team:research-authors
    last_modified: 2025-05-05
  - id: storage-correctness-survey-2026
    resource: https://arxiv.org/abs/2602.02614
    title: "Testing Storage-System Correctness: Challenges, Fuzzing Limitations, and AI-Augmented Opportunities"
    author: team:research-authors
    last_modified: 2026-02-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# TF Discussion Statement

> PROVE does not merely generate many input combinations. It understands verification intent and SSD state transitions, selects Test Cases that can expose meaningful failures, and uses execution Evidence to expand the verification space continuously.

A shorter expression is:

> **Understand meaning, explore state, and expand through evidence.**

# Why the Original Phrase Needs Refinement

Saying that AI should generate Cases "instead of random inputs" can incorrectly reject useful exploratory randomness. Randomization and fuzzing can reveal unknown behavior, but unguided enumeration alone does not explain why a Case matters or whether it reached a meaningful storage state.

The proposed direction combines:

1. **Semantic guidance** — Requirement, verification intent, risk, expected invariant, and Oracle explain what the Case must challenge.
2. **State guidance** — Preconditions, device and environment history, transition, intervention point, recovery, and post-state explain where and when to challenge it.
3. **Exploratory variation** — Controlled randomness and combinatorial exploration search beyond already-known examples.
4. **Execution feedback** — Evidence of reached states, unexpected behavior, failures, and gaps guides the next Case.

# Relationship to Scenario, Case, and Script

```text
Test Scenario
defines meaningful verification intent and space
        ↓
Test Case generation and selection
chooses concrete states, transitions, parameters, and paths
        ↓
Test Script
executes the Case through a replaceable runtime
        ↓
Evidence and disposition
prove what happened and guide the next exploration
```

Scenario is the primary long-term asset. Test Case generation is a core capability that fills the Scenario-defined space. Test Script is a replaceable implementation.

Generated Cases and their scheduling must follow the stable [Stateful Test Sequencing](/principles/stateful-test-sequencing.md) rules: compatible state may be reused, dependencies must be explicit, and sequence-dependent Failures must be traced to their causal state transitions.

# Minimum Explanation Expected from a Generated Case

Before promotion, a generated Case should be able to explain:

- Which Scenario and Requirements it serves
- Which starting state and transition it targets
- Why its parameters, sequence, and intervention point were selected
- Which failure or invariant it is intended to expose
- Which Oracle and Evidence make the result decidable
- What new information its execution contributed

# TF Questions

- What is the minimum useful representation of SSD and relevant environment state?
- How is verification meaning represented without reducing it to document similarity?
- How should known-risk Cases and exploratory Cases be balanced?
- What feedback qualifies as a new state, a Coverage Gap, or redundant execution?
- When is a generated Case retained as a regression asset rather than regenerated on demand?

# Decision Boundary

This proposal does not define a Coverage axis, state model, selection algorithm, weight, or acceptance threshold. Those decisions require verification-expert review and an ADR.
