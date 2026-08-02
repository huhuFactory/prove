---
type: Source Summary
title: PROVE Leader Stateful Test Sequence Directive — 2026-08-02
description: Explicit confirmation of state reuse, declared dependencies, and sequence-dependent Failure handling.
tags: [prove, source, state, test-sequence, failure]
status: stable
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
verified: { by: "human:prove-leader", at: "2026-08-02T00:00:00+09:00" }
---

# Confirmed Direction

- Test Cases may reuse Device state when the previous Case's observed Post-State satisfies the next Case's required Pre-State.
- Hidden execution-order dependencies are not acceptable; required and produced states must be explicit and traceable.
- A Failure observed in a later Case may originate from state created by an earlier Case.
- Sequence-dependent findings must not be dismissed as coincidence. PROVE should reproduce, minimize, analyze, and promote meaningful sequences into verification assets.
- Test Case dependencies should be represented primarily through state requirements and effects rather than an unmaintainable graph of Test identifiers.
