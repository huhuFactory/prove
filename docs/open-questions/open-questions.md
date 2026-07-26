---
type: Open Questions
title: PROVE Open Questions
description: Decisions and facts that must remain unresolved until explicitly confirmed.
tags: [prove, questions, decisions]
status: draft
sources:
  - id: discovery-2026-07-26
    resource: /sources/discovery-interview-2026-07-26.md
    title: PROVE leader discovery discussion
    author: human:prove-leader
    last_modified: 2026-07-26
  - id: core-directive-2026-07-27
    resource: /sources/coverage-core-directive-2026-07-27.md
    title: PROVE leader Coverage core directive
    author: human:prove-leader
    last_modified: 2026-07-27
generated: { by: openai-codex/gpt-5, at: "2026-07-27T00:00:00+09:00" }
---

# Product and Evaluation

- How is the verification space representing 100% constructed and bounded?
- What dimensions and computation define Test Case Coverage?
- How is Verification Intent represented and extracted from legacy tests?
- What evidence independently proves Intent preservation?
- What evidence independently proves actual defect-detection preservation?
- How is reusable engineering knowledge applied to a new specification?
- What evidence demonstrates that an AI-generated Test Case is useful?
- Which specification versions and fewer-than-ten features are selected first?
- How are conflicting or extending requirements across specifications handled?
- How many representative device and non-device failures can be curated?

# IceT and Execution

- What is the exact SSD Verification Specification for the new IceT?
- Is C++ formally selected as the Test Case language?
- What core primitives, runtime, API, build, and dependency model are required?
- Which existing IceT layers remain, change, or disappear?
- What common contract serves engineer-assigned systems and SkyTower?
- When are the eight execution systems confirmed?

# SkyTower and Integrations

- What are SkyTower's current internal agents, services, data models, and responsibilities?
- What PROVE-facing API replaces or adapts its current heavy interface?
- What API and ownership agreement is available for the downstream failure system?
- Can PROVE modify the internal Spec RAG, or only query it?

# Failure Governance

- What confidence or evidence threshold permits autonomous disposition?
- Who is accountable for incorrect PROVE classifications?
- What repair, recovery, and retry limits apply?
- What exact report schema accompanies handoff or human escalation?

# Knowledge and Organization

- Who owns each workstream and Root Knowledge?
- What are the precise organizational meanings of eSSD and cSSD?
- What retention and deletion policy applies to prompts, logs, and generated artifacts?
- What approval is required before customer specifications enter a commercial LLM?
- What are the final repository names and internal Git URLs?

# Resolution Rule

Every resolved question must link to an ADR or verified concept update. Do not delete historical questions without recording their resolution.

Coverage-axis questions remain open by deliberate decision, not by omission.
