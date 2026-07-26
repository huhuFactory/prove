---
type: Governance
title: PROVE Decision Process
description: How proposals, experiments, decisions, and unresolved questions become durable knowledge.
tags: [prove, governance, adr, decisions]
status: draft
sources:
  - id: discovery-2026-07-26
    resource: /sources/discovery-interview-2026-07-26.md
    title: PROVE leader discovery discussion
    author: human:prove-leader
    last_modified: 2026-07-26
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Decision Classes

| Class | Example | Location |
|---|---|---|
| Root | Coverage definition, failure taxonomy, common identifiers | Root `docs/decisions/` |
| Cross-project interface | IceT execution contract, SkyTower result contract | Root plus owning repositories |
| Local architecture | IceT runtime implementation | Owning repository |
| Experiment | Model, prompt, parser, or workflow comparison | Owning repository evaluations |

# Process

1. Record ambiguity in [Open Questions](/open-questions/open-questions.md).
2. Name an owner and required evidence.
3. Write a proposal or experiment plan.
4. Compare alternatives and consequences.
5. Record the decision in an ADR.
6. Update affected concept pages.
7. Append the change to `log.md`.
8. Notify and version affected subprojects.

# Decision Status

Use `proposed`, `accepted`, `superseded`, or `rejected` inside ADR content. OKF lifecycle state remains separate: a newly accepted but unreviewed document can still be `draft`.

# No Silent Resolution

An agent encountering a conflict must report it. It may propose options, but it must not choose a policy, scope, owner, security boundary, or success criterion without authority.
