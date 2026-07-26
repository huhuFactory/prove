---
type: Architecture Decision
title: "ADR-0001: Establish a federated PROVE Root Knowledge Bundle"
description: Decision to manage shared PROVE knowledge in a dedicated OKF repository.
tags: [prove, adr, knowledge, okf]
status: draft
sources:
  - id: discovery-2026-07-26
    resource: /sources/discovery-interview-2026-07-26.md
    title: PROVE leader discovery discussion
    author: human:prove-leader
    last_modified: 2026-07-26
  - id: okf-spec
    resource: https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md
    title: Open Knowledge Format v0.2
    author: team:google-cloud
    last_modified: 2026-07-24
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Status

Proposed; pending TF review.

# Context

PROVE will contain independently versioned subprojects such as IceT, SkyTower, scenario extraction, test generation, and failure analysis. All must remain aligned to shared goals and terminology while owning their implementation knowledge.

# Decision

- Maintain shared knowledge in a dedicated Root Git repository.
- Give every subproject an independent repository and local `docs/` bundle.
- Use the Karpathy LLM Wiki pattern for continuous knowledge compilation.
- Represent concepts using OKF v0.2 Markdown and frontmatter.
- Pin each subproject to an explicit Root release and commit.
- Promote cross-project knowledge through reviewed upstream changes.

# Consequences

Benefits:

- Reproducible project context for humans and agents
- Explicit ownership and lifecycle
- Reduced terminology drift
- Traceable cross-project decisions

Costs:

- Root release and dependency-upgrade process
- Required curation and review
- Cross-repository link and tooling work
- Risk of stale subproject locks

# Follow-Up

- Assign the Root Knowledge Owner.
- Approve metadata and review rules.
- Select the internal Git repository URL.
- Implement link and conformance validation.
- Create initial subproject repositories and locks.
