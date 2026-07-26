---
type: Architecture
title: PROVE Knowledge Architecture
description: Federated Root and subproject knowledge model using LLM Wiki and OKF.
tags: [prove, knowledge, llm-wiki, okf]
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

# Model

PROVE uses a federated knowledge model:

- This Root repository owns shared purpose, terminology, principles, capability boundaries, metrics, and interfaces.
- Every subproject has an independent Git repository and its own `docs/` OKF bundle.
- Subprojects pin the Root version used for their decisions.
- Shared discoveries flow upstream through review; Root releases flow downstream through explicit upgrades.

# Knowledge Flow

```mermaid
flowchart TD
    Sources["Sources, discussions, experiments"] --> Compile["LLM Wiki compilation"]
    Compile --> Draft["Draft concept update"]
    Draft --> Review["Human or defined verification"]
    Review --> Root["Root Knowledge release"]
    Root --> Lock["Subproject knowledge lock"]
    Lock --> Local["Local knowledge and implementation"]
    Local --> Proposal["Shared discovery or conflict proposal"]
    Proposal --> Draft
```

# Source-of-Truth Rule

Root content must not be manually copied into subproject documentation. A subproject records the Root repository, release, and commit in `prove-knowledge.lock`. A fetched or generated cache is allowed, but it is not authoritative.

# LLM Wiki Rule

Agents should update existing concepts, connect related concepts, expose contradictions, preserve sources, and append meaningful changes to `log.md`. They must not convert an unresolved question into a fact.

# OKF Rule

- Bundle version: OKF v0.2
- Every non-reserved Markdown concept has YAML frontmatter and `type`.
- `index.md` and `log.md` follow reserved-file rules.
- `generated` identifies the current producer.
- `verified` is added only after actual verification.
- `status` uses `draft`, `stable`, or `deprecated`.

# Release Rule

Root releases use semantic versions. A subproject upgrade must review affected terminology, principles, interfaces, and decisions before changing its lock.
