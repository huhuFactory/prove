---
type: Concept Model
title: Test Version and Official Adoption
description: Minimal lifecycle model for versioning, validating, adopting, deprecating, and rolling back PROVE Test Cases.
tags: [prove, test, version, validation, package, baseline]
status: draft
sources:
  - id: test-version-and-adoption-directive-2026-08-02
    resource: /sources/test-version-and-adoption-directive-2026-08-02.md
    title: Test Version and official adoption directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Minimal Model

```text
Test Case
├─ stable Test ID
├─ immutable Version
├─ Status: Draft / Validated / Deprecated
└─ linked Validation Evidence
```

The model deliberately avoids representing generation, execution, Coverage evaluation, Package adoption, and every context as separate Test lifecycle states.

# Official Adoption

A Test Version is official for a Package or Gate Baseline when the applicable immutable Manifest references that exact Version.

```text
Validated Test v1.3
→ Package or Gate Baseline Manifest references v1.3
→ v1.3 is official within that Manifest's context
```

This allows one Test identity to be reused without maintaining a separate adoption-state matrix inside the Test itself. Applicability and team selection still determine whether the Test belongs in a particular Manifest.

# Events and Evidence

Generation, static validation, Hardware execution, repeated execution, and Coverage evaluation are versioned events or Evidence linked to the Test Version. They do not permanently advance the Test through a long linear state chain.

The exact Evidence required for `Validated` remains open and must align with [Test Execution Qualification](/concepts/test-execution-qualification.md).

# Change, Deprecation, and Rollback

- Modification creates a new Test Version and requires applicable revalidation.
- Deprecation blocks new adoption while preserving historical references and Evidence.
- Historical Package and Gate Baseline Manifests remain immutable.
- Rollback creates a new Package Manifest or successor Baseline that references a prior valid Test Version; it does not move an old tag or rewrite history.

# Open Detail

The identifier format, Version scheme, status authority, minimum Validation Evidence, Package Manifest contract, and deprecation or restoration approval remain to be defined.
