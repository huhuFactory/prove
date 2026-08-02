---
type: Concept Model
title: Scenario Candidates and Canonical Scenarios
description: Working model for integrating Scenarios from Specifications, Legacy Packages, FLAIR, and engineer knowledge without losing source meaning.
tags: [prove, scenario, canonicalization, integration, traceability]
status: draft
sources:
  - id: scenario-canonicalization-directive-2026-08-02
    resource: /sources/scenario-canonicalization-directive-2026-08-02.md
    title: PROVE leader Scenario canonicalization and traceability directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Purpose

PROVE receives verification intent from different Sources: formal Specifications, Legacy Test Packages, FLAIR development context, and verification engineers. These Sources may express the same intent differently, extend one another, or conflict. Integration must create reusable Scenario assets without erasing their origin or meaning.

# Working Model

```text
Versioned Source
  → Requirement or extracted knowledge
  → Source Scenario Candidate
  → mapping decision
  → Canonical Scenario or Scenario Variant
  → Test Case and executable Test Script
```

- **Source Scenario Candidate** preserves the meaning extracted from one Source and version.
- **Canonical Scenario** represents a shared verification intent recognized across Sources.
- **Scenario Variant** retains a meaningful product, customer, policy, or condition-specific difference without duplicating the shared intent.
- **Mapping decision** records whether a Candidate is equivalent, extending, variant, conflicting, or unresolved.

Canonicalization is non-destructive. A Canonical Scenario does not replace its Candidates, and a later remapping does not erase the earlier decision.

# Mandatory Traceability

Every relationship must be navigable in both directions. From a Source change, PROVE must identify affected Requirements, Candidates, Canonical Scenarios, Cases, executions, Evidence, and verdicts. From any Failure or Case, PROVE must reconstruct the originating Sources, transformations, mapping decisions, and versions.

Each mapping must retain its status, rationale, author or Agent, supporting Evidence, time, and applicable versions. Merge, split, supersession, variant, and conflict histories are part of the knowledge asset.

# Unresolved Design

The hierarchy of the Canonical Scenario catalog, exact identity rules, conflict authority, and storage schema remain open. These choices must preserve complete lineage and must not establish Coverage dimensions before expert approval.
