---
type: Concept Model
title: Verification Baselines and Development Gates
description: Working model for freezing reproducible verification configurations at Main and Deri development gates.
tags: [prove, baseline, git, versioning, main, deri, gate]
status: draft
sources:
  - id: verification-baseline-directive-2026-08-02
    resource: /sources/verification-baseline-directive-2026-08-02.md
    title: PROVE leader Verification Baseline directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Definition

A Verification Baseline is an immutable, approved manifest of the exact version references used as the verification basis at a formal project gate. It is not a copy of every referenced artifact and is not created for every change.

```text
Continuously changing Working View
→ project Gate review
→ immutable Verification Baseline
→ later changes continue in the next Working View
```

Each Main and Deri project creates Baselines according to its own schedule and gate instances. A Deri Baseline may inherit from whichever approved Main Baseline it actually derives from; matching gate names or dates are not required.

# Manifest Contents

A Baseline may reference:

- Source Specification and Requirement revisions
- Verification Knowledge and Scenario catalog revisions
- Test Case package revisions
- Product Profile and applicability configuration
- Firmware build identifiers and content digests
- IceT and relevant execution-contract versions
- Known exceptions, deferred Requirements, and Coverage Gaps

The exact schema remains open.

# Git Tag Model

Git can manage Baseline identity effectively when a dedicated manifest commit resolves all cross-repository and database references. An annotated, protected tag identifies the approved Gate Baseline.

```text
baseline/firenze-main/ws1
baseline/firenze-main/ws2
baseline/firenze-deri-a/ws1
baseline/firenze-deri-a/es1
```

Do not depend on independently named tags across every component repository as the sole source of truth. The manifest should pin immutable component references such as Git commit IDs, database snapshot IDs, firmware build IDs, and artifact digests.

If an approved Baseline needs correction, create a successor such as `ws1.1`; do not move or rewrite the existing tag.

If referenced Knowledge is later revoked, preserve the original Baseline and attach the invalidation or impact relationship. Create and approve a successor Baseline when the project's correction policy requires one; do not rewrite the historical manifest.

# Recommended Workflow

```text
1. PROVE resolves the current Working View
2. Automation generates a candidate Baseline manifest
3. Validation checks that every reference is immutable and accessible
4. Reviewers approve the manifest at the project Gate
5. Git creates a protected annotated tag
6. A registry or database indexes the tag for search and impact analysis
```

The number of tags may be large, but each tag identifies a small immutable manifest. Automation, naming conventions, and indexing prevent the administrative burden associated with copied Baselines.

# Baseline Versus Run Manifest

- **Verification Baseline**: approved configuration intended for a project Gate.
- **Run Manifest**: automatically captured configuration actually used by one execution.

Run Manifests may exist between formal gates without creating additional Baselines.

# Decision Status

Gate-aligned Baselines, independent project schedules, and Main/Deri inheritance are confirmed. The canonical Git repository, tag naming convention, manifest schema, approval workflow, database index, and access policy remain implementation decisions.
