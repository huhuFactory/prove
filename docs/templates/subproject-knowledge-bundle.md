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
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
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
2. Load the pinned Root vision, glossary, principles, capabilities, and interfaces.
3. Read local `docs/project.md`.
4. Read relevant local requirements and accepted ADRs.
5. Report unresolved conflicts before implementing.

# Promotion Rule

Propose an upstream Root change when local knowledge affects more than one subproject or changes common terminology, principles, metrics, capabilities, or contracts.
