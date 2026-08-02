---
type: Source Summary
title: PROVE Leader Legacy Scenario Analysis Directive — 2026-08-02
description: Confirmation that Legacy Package code analysis is limited to what Scenario and Verification Knowledge extraction require.
tags: [prove, source, legacy, scenario, test-library]
status: stable
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
verified: { by: "human:prove-leader", at: "2026-08-02T00:00:00+09:00" }
---

# Confirmed Direction

- The primary purpose of Legacy Test Package analysis is to extract Test Scenarios and reusable Verification Knowledge.
- A complete Call Graph or Code Dependency model for more than 20,000 Tests is not a PROVE objective.
- Code and Library paths are analyzed only as far as needed to understand Scenario intent, stimulus, state effects, Oracle, recovery, applicability, and evidence.
- Relevant Code relationships remain provenance and confidence Evidence for extracted knowledge rather than the final knowledge asset.
- Legacy State dependencies are not currently declared or managed, so their existence is unknown. Candidate state effects may be observed and later converted into explicit PROVE State Contracts.
