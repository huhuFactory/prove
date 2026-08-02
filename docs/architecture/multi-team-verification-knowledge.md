---
type: Architecture
title: Multi-Team Verification Knowledge Operation
description: Draft operating architecture for accepting multi-team inputs while preserving shared identities, contextual views, and full Traceability.
tags: [prove, architecture, multi-team, knowledge, traceability, deployment]
status: draft
sources:
  - id: verification-organization-and-selection-directive-2026-08-02
    resource: /sources/verification-organization-and-selection-directive-2026-08-02.md
    title: Verification organization and Test selection directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Problem

PROVE will receive concurrent inputs from organizations with different R&R, product families, time budgets, Hardware, customer obligations, and project schedules. eSSD adds substantial customer-specific Specifications, requested OCP versions, TP inputs, and Deri-specific combinations. A single flat list would mix contexts; independent team copies would recreate duplication and break Global Traceability.

# Proposed Operating Model

Use one shared verification identity and Traceability plane with logically separated team and project workspaces.

```text
Immutable Source Registry
        ↓
Canonical Requirement–Scenario–Case Graph
        ↓
Context relationships
  ├─ Organization and R&R
  ├─ eSSD or cSSD product context
  ├─ Main or Deri project
  ├─ Customer, OCP, and TP obligations
  └─ Gate Baseline and execution environment
        ↓
Team/Project Verification View
        ↓
Selection, execution, Evidence, and verdict
```

This is a graph of relationships, not a rigid folder tree. One Source, Requirement, Scenario, or Case may participate in several valid contexts without being copied.

# Confirmed Direction and Deferred Detail

The use of one common PROVE system and one shared logical Knowledge and Traceability plane is confirmed. Independent authoritative PROVE instances per verification team are not the target.

The exact Workspace, View, ownership, review, permission, conflict-resolution, and promotion mechanisms remain draft. They must be designed later with experts representing the participating verification teams.

# Four Logical Layers

1. **Source Registry** preserves each submitted document, Package, policy, TP, and version with its owner and provenance.
2. **Canonical Verification Graph** manages shared Requirement, Scenario, Case, and Traceability identities while preserving Source Candidates and Variants.
3. **Context Overlay** states where an asset applies: team, product, Main/Deri, customer, project, Specification version, Gate, and environment.
4. **Team/Project View** resolves the relevant assets for selection and execution without creating a new authoritative copy.

# Deployment Boundary

Agent execution may occur on an engineer system or through SkyTower, but both should use the same shared identity and Traceability plane. Local operation may cache or stage work; it must not create an untraceable independent knowledge universe.

The Root Knowledge repository defines this shared operating rule. Customer Specifications, project Requirements, Scenario records, Cases, and Run Evidence belong in the future operational registry and owning repositories rather than being copied into Root documentation.

# Input and Promotion

New team input first remains attributable to its Source and context. It may map to existing canonical knowledge, create a Variant, expose a conflict, or propose shared knowledge. Immediate submission must not automatically make it enterprise-verified knowledge. The detailed review and promotion policy belongs to work item 9.

Applicability Scope and Trust State are independent. Team, project, Main/Deri, customer, product, and Global context describe where Knowledge applies; they do not rank its quality. See [Verification Knowledge Scope and Trust](/concepts/knowledge-scope-and-trust.md).

# Required Properties

- Stable identifiers across teams and systems
- Versioned, bidirectional Traceability
- Source preservation and non-destructive mapping
- Context-aware views rather than copied Test Packages
- Explicit conflict and unresolved states
- Reproducible Gate Baselines and Run Manifests
- Query from any result back to team, project, customer obligation, Source, and transformation history

# Open Decisions

The physical storage technology, service topology, offline policy, Workspace and View model, ownership, approval workflow, and synchronization protocol are not selected.
