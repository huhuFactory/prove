---
type: Interface Map
title: PROVE Integration Boundaries
description: Known cross-system exchanges and interface decisions still required.
tags: [prove, interfaces, icet, skytower, rag]
status: draft
sources:
  - id: discovery-2026-07-26
    resource: /sources/discovery-interview-2026-07-26.md
    title: PROVE leader discovery discussion
    author: human:prove-leader
    last_modified: 2026-07-26
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Boundaries

| Boundary | Known state | Required contract |
|---|---|---|
| Spec RAG → PROVE | Read access exists; change access unknown | Versioned query, source identity, retrieval evidence, data policy |
| PROVE → IceT | Existing IceT uses JS and high-level feature APIs; redesign is considered | Test artifact, build, execution request, device control, result |
| PROVE → SkyTower | APIs exist but are considered too heavy for PROVE without adaptation | Lightweight job, state, evidence, retry, and cancellation model |
| IceT → DUT controls | Broad pyNVMe-class control plus internal sideband and driver capabilities | Capability discovery, invocation, evidence, recovery |
| PROVE → downstream failure system | Target system exists; API requires owner discussion | Handoff package, status, correction feedback |
| PROVE → official Test Package | Automatic validated promotion is intended | Version, validation evidence, compatibility, rollback, ownership |
| FW development → PROVE | SRS, policy, source, and generated code are accessible | Change context, affected behavior, test request, feedback |

# Common Identity Needs

Contracts should share stable identifiers for:

- Source and requirement
- Scenario and Test Case
- Package and version
- Execution and retry lineage
- DUT, FW, platform, and environment
- Failure, disposition, repair, and handoff
- Model, agent workflow, prompt, and tool

# Evidence Rule

An interface must not return only a summary verdict. It must provide or reference the evidence needed to reproduce and audit that verdict.
