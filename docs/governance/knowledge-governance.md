---
type: Governance
title: PROVE Knowledge Governance
description: Ownership, lifecycle, and federated update rules for Root and subproject knowledge.
tags: [prove, governance, knowledge, okf]
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
  - id: discovery-2026-08-02
    resource: /sources/discovery-2026-08-02.md
    title: PROVE working discovery discussion
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Ownership

- Root Knowledge Owner: unassigned
- Concept Owner: accountable domain role or team
- Producer: human, agent, or process that made the current content
- Verifier: human or process that checked the content against evidence

The producer and verifier should be different for high-impact policies and metrics.

The same separation applies to operational Verification Knowledge. A generating Agent cannot grant its own official Trust State. During initial operation, final Verified promotion belongs to the accountable expert for the target Knowledge scope, supported by independent evaluation Evidence.

# Lifecycle

| State | Meaning |
|---|---|
| `draft` | Incomplete, proposed, or not reviewed |
| `stable` | Reviewed and ready for project consumption |
| `deprecated` | Retained for history but no longer current |

New concepts default to `draft`. Agents cannot add a `human:` verification event without explicit human confirmation.

This OKF document lifecycle is separate from operational Verification Knowledge governance. Operational Knowledge uses independent applicability-scope and Trust dimensions as described in [Verification Knowledge Scope and Trust](/concepts/knowledge-scope-and-trust.md). A document becoming `stable` does not automatically make the Knowledge it describes operationally Verified.

# Evolving Discovery

Project-leader statements may be exploratory and may change during planning. Use this flow:

```text
Dated discussion summary
→ draft concept synthesis
→ conflict and impact review
→ explicit decision or verification
→ stable concept
```

- Preserve each dated source even when later thinking changes.
- Update the current concept and `log.md`; do not rewrite the historical source.
- A direct statement is evidence of what was said, not automatic approval of every derived design detail.
- Only explicit confirmation may add a `human:` verifier or promote content to `stable`.
- When a new draft conflicts with a stable concept, record the conflict and request a decision instead of silently replacing the stable rule.

# Root Versus Local

Root owns knowledge used by multiple subprojects. A subproject owns local requirements, implementation design, API details, experiments, and runbooks. A local concept is promoted when it changes shared vocabulary, goals, principles, metrics, capabilities, or cross-project contracts.

Knowledge governance is one specialization of the broader [Artifact Lifecycle and Governance](/governance/generated-artifact-governance.md). Requirement, Scenario, Coverage, Test, execution, Evidence, Failure, Agent, and manifest Outputs also require explicit Input lineage and Review Records.

# Change Requirements

Every material change identifies:

- Reason and evidence
- Affected concepts and subprojects
- Compatibility or migration impact
- Remaining uncertainty
- Required re-verification

# Review Cadence

- Review open questions and recent knowledge changes during the weekly TF update.
- Review stale and draft high-impact concepts before milestone decisions.
- Review Root-version impact when a subproject upgrades its lock.

# Retention

Long-term retention is allowed. Exact retention, deletion, and deprecation rules remain a TF decision.
