---
type: Source Summary
title: Test Version and Official Adoption Directive — 2026-08-02
description: Confirmation of the minimal Test lifecycle model using immutable versions, validation Evidence, and Package or Baseline references.
tags: [prove, source, test, version, package, baseline]
status: stable
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
verified: { by: "human:prove-leader", at: "2026-08-02T00:00:00+09:00" }
---

# Confirmed Direction

- Keep the Test lifecycle model minimal rather than managing many independent adoption dimensions.
- A Test Case has a stable identity, immutable Version, a simple Draft, Validated, or Deprecated status, and linked Validation Evidence.
- Generated, Executed, and Coverage Evaluated are events or Evidence, not permanent lifecycle states of the Test.
- A Test Version is official for a Package or Gate Baseline when that immutable Manifest references it.
- Test modification creates a new Version; it does not overwrite the prior Version.
- Rollback or correction creates a new Package Manifest or successor Baseline that references a prior valid Test Version; an approved historical Baseline is not rewritten.
- Deprecated Versions remain available for historical Traceability but cannot be newly adopted unless an explicit correction decision restores them through versioned governance.
