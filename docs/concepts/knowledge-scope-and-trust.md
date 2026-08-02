---
type: Concept Model
title: Verification Knowledge Scope and Trust
description: Working two-dimensional governance model separating where Knowledge applies from how strongly it has been validated.
tags: [prove, knowledge, scope, trust, governance]
status: draft
sources:
  - id: knowledge-scope-and-trust-directive-2026-08-02
    resource: /sources/knowledge-scope-and-trust-directive-2026-08-02.md
    title: Verification Knowledge scope and trust directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Principle

PROVE manages Verification Knowledge using independent dimensions rather than a single Global–Team–Project–User hierarchy.

```text
Applicability Scope: where and under which context the Knowledge is valid
Trust State: how strongly the Knowledge has been reviewed and validated
Ownership and Provenance: who supplied it and from which Sources
```

A project-specific item can be highly validated, while a globally visible proposal can remain unverified. Moving Knowledge to a broader scope must not imply that its quality increased.

# Applicability Scope

Candidate context types include User, Team, Project, Main/Deri, Customer, Product, and Global. Scope is a set of graph relationships rather than one fixed parent path, so one Knowledge item may validly apply to several contexts.

Every scope relationship must record its applicable versions, conditions, exclusions, owner, rationale, and change history. Exact context types and precedence rules remain open.

# Operational Trust State

The current candidate lifecycle is:

```text
Draft → Candidate → Validated → Verified → Deprecated
```

This lifecycle is provisional. Evidence requirements, approvers, regression rules, demotion, revocation, and emergency correction remain to be defined with verification-team experts.

# Promotion Without Copying

Promotion changes reviewed scope and Trust relationships while preserving one Knowledge identity and its Source history. It must not copy the content into an unrelated Global store or erase the narrower context from which it originated.

Conflicting Knowledge may coexist in explicit contexts until an authorized decision resolves the conflict. Global visibility, Global applicability, and Verified Trust are distinct claims.

# Experimental Use Boundary

Draft Knowledge may be selected immediately for an explicitly labeled experimental workflow. Its input, generated assets, runs, Evidence, and effects must remain traceable to the Draft version.

Until the required official-use Trust State is reached, Draft Knowledge must not directly:

- Satisfy an official Coverage claim
- Determine a project official Pass/Fail result
- Enter an official Test Package
- Enter an approved Gate Baseline as accepted Verification Knowledge

Experimental results and expert Feedback may become promotion Evidence. The exact Trust State required for each official use remains open.

# Initial Promotion Authority

Knowledge production and verification are separated. A generating human or Agent may submit Knowledge and promotion Evidence but may not independently grant its own official Trust.

The initial working model is:

```text
Draft      → produced by a user or Agent
Candidate  → proposed with automated or human Evidence
Validated  → checked by an independent Agent, Harness, or reviewer
Verified   → approved by the accountable expert for the target scope
```

Project or Team scope uses its responsible verification expert. Product, Customer, or Global scope requires the accountable domain experts affected by that scope. Exact role names, quorum, workflow, and Evidence thresholds remain open.

PROVE may expand automated promotion later after the evaluation mechanism itself is proven. This future option does not permit self-promotion by the Knowledge-producing Agent.

# Revocation and Correction

Officially used Knowledge is immutable by version. When it is found incorrect:

```text
Revoke affected version from future use
→ traverse Traceability for impacted Requirements, Scenarios, Cases,
  Coverage results, runs, verdicts, Packages, and Baselines
→ create a corrected Knowledge version
→ revalidate affected current assets and claims
→ append invalidation or supersession relationships to history
```

Revocation blocks future use but does not erase the earlier version. Existing Gate Baselines and Run Manifests continue to reference exactly what was used at the time. A rollback means explicitly selecting a prior valid version as a new current decision, not rewriting history.

# Documentation Boundary

Operational Trust State applies to Verification Knowledge consumed by PROVE. It is separate from the OKF page lifecycle values `draft`, `stable`, and `deprecated`, which describe the review state of documents in this Root bundle.
