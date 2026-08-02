---
type: Source Summary
title: PROVE Leader Verification Baseline Directive — 2026-08-02
description: Confirmation that Main and Deri projects freeze verification configurations at their own formal development gates.
tags: [prove, source, baseline, main, deri, gate]
status: stable
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
verified: { by: "human:prove-leader", at: "2026-08-02T00:00:00+09:00" }
---

# Confirmed Direction

- PROVE should align Verification Baselines with existing formal development gates such as WS and ES rather than create a Baseline for every change.
- Main and Deri projects use the same general gate model, but every project has its own schedule and gate instances.
- Customer Requirements and other changes continue in a Working View and enter the applicable project Gate Baseline according to their effective target.
- A Baseline is a versioned manifest of references, not a physical copy of all source, knowledge, Test, firmware, and execution assets.
- Main and Deri Baselines may use inheritance and delta overlays where their verification configurations are shared.
