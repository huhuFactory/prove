---
type: Adoption Strategy
title: PROVE Adoption and Global Package Migration
description: Current working strategy for Firenze adoption and gradual Test Package convergence.
tags: [prove, firenze, migration, global-package, legacy]
status: draft
sources:
  - id: discovery-2026-08-02
    resource: /sources/discovery-2026-08-02.md
    title: PROVE working discovery discussion
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Global Package Position

Global Test Package integration is not a forced physical merge. It is the expected long-term result of producing validated Tests through PROVE and migrating package areas gradually.

# Knowledge Baseline

- Four verification teams and their Test Packages are in scope.
- The working baseline is each team's package state around August 2026.
- PROVE extracts Test Scenarios and reusable engineering knowledge from those package snapshots.
- Earlier project environments are not retroactively brought under PROVE management.
- Selected historical execution, Failure, and Bug information may still strengthen knowledge and defect-detection evidence.

Exact baseline commits or tags are not yet recorded.

# Migration Unit

A legacy Test is migrated only after PROVE regenerates an executable Test from the extracted Scenario and evaluates both:

1. Verification Intent preservation.
2. Actual defect-detection capability preservation.

Migration is expected to take approximately six months or longer. Existing and PROVE-generated Tests may coexist during that period.

# Firenze

Firenze is the first real-project PROVE pilot, not the full cutover point.

- Existing IceT and legacy Test Packages remain in official use.
- PROVE-generated Tests also contribute to official Pass/Fail decisions.
- PROVE is refined using gaps and failures observed in actual project operation.
- Full PROVE use is targeted for the project after Firenze, subject to Firenze evidence and later decisions.

# Change Control

This strategy is a current working position, not a stable commitment. Changes must preserve the dated source and update this concept rather than rewriting history silently.
