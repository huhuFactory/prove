---
type: Template
title: PROVE Subproject Knowledge Bundle Template
description: Required structure and starter content for an independent PROVE subproject repository.
tags: [prove, template, subproject, knowledge]
status: draft
sources:
  - id: root-knowledge-architecture
    resource: /architecture/knowledge-architecture.md
    title: PROVE Knowledge Architecture
    author: openai-codex/gpt-5
    last_modified: 2026-07-26
  - id: root-core-value
    resource: /principles/core-value.md
    title: PROVE Core Value
    author: human:prove-leader
    last_modified: 2026-07-27
generated: { by: openai-codex/gpt-5, at: "2026-07-27T00:00:00+09:00" }
---

# Repository Structure

```text
subproject/
├── AGENTS.md
├── README.md
├── prove-knowledge.lock
└── docs/
    ├── index.md
    ├── project.md
    ├── requirements/
    ├── architecture/
    ├── interfaces/
    ├── decisions/
    ├── evaluations/
    ├── runbooks/
    └── log.md
```

# `prove-knowledge.lock`

```yaml
schema_version: 1
repository: "<internal PROVE Root Knowledge URL>"
version: "<release tag>"
commit: "<exact commit SHA>"
```

# Required `project.md` Content

- Mission and expected outcomes
- Explicit contribution to the PROVE Core Value
- Root capabilities owned
- In-scope and out-of-scope work
- Inputs and outputs
- Upstream and downstream interfaces
- Success evidence
- Owners
- Root Knowledge version
- Open questions and risks

# Required Agent Read Order

1. Read `prove-knowledge.lock`.
2. Load the pinned `/principles/core-value.md`.
3. Load the pinned Root vision, glossary, remaining principles, capabilities, and interfaces.
4. Read local `docs/project.md`.
5. Read relevant local requirements and accepted ADRs.
6. Report unresolved conflicts before implementing.

# Core Alignment Rule

The subproject and every Agent must treat its implementation technology as replaceable. It must not define a Coverage axis as authoritative or claim package equivalence from Test Case count, code similarity, or semantic similarity alone.

# Promotion Rule

Propose an upstream Root change when local knowledge affects more than one subproject or changes common terminology, principles, metrics, capabilities, or contracts.
