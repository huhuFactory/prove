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
  - id: discovery-2026-08-02
    resource: /sources/discovery-2026-08-02.md
    title: PROVE working discovery discussion
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Product and Evaluation

- How is the verification space representing 100% constructed and bounded?
- What dimensions and computation define Test Case Coverage?
- How is Verification Intent represented and extracted from legacy tests?
- What evidence independently proves Intent preservation?
- What evidence independently proves actual defect-detection preservation?
- How is reusable engineering knowledge applied to a new specification?
- What is the approved granularity and schema of a Verification Pattern?
- What state and semantic model should guide Test Case generation without excluding exploratory randomness?
- How are generated Cases selected, explained, retained, and fed back after execution?
- What State Contract schema represents Pre-State, state effects, Post-State, and cleanup or preservation policy?
- How is state compatibility verified when relevant SSD internal state is only partially observable?
- How are hidden sequence dependencies extracted and validated from the four legacy Test Packages?
- What evidence demonstrates that an AI-generated Test Case is useful?
- Which actual Spec, Feature, and subset of the four verification-team packages demonstrate the first Coverage system?
- Which specification versions and fewer-than-ten features are selected first?
- How many extracted Legacy Scenarios across the four Package Baselines require expert attestation before Milestone Review 5?
- How are conflicting or extending requirements across specifications handled?
- Should the Canonical Scenario catalog be a flat enterprise catalog or a layered Core and product, Main, customer, or Deri Variant model?
- What identity, equivalence, merge, split, and supersession rules govern Scenario canonicalization?
- Who has authority to resolve conflicting Scenario Candidates, and what Evidence is required?
- How many representative device and non-device failures can be curated?
- What minimum Evidence and authority change a Test Version from Draft to Validated?

# IceT and Execution

- What acceptance thresholds and repetition policy apply to each Test qualification area?
- Must every generated Test Case and parameter variation complete real-Hardware qualification, or can an approved equivalence and sampling policy apply before official promotion?
- What is the exact SSD Verification Specification for the new IceT?
- Is C++ formally selected as the Test Case language?
- What core primitives, runtime, API, build, and dependency model are required?
- Which existing IceT layers remain, change, or disappear?
- What common contract serves engineer-assigned systems and SkyTower?
- What exact identity, Capability, configuration, and availability metadata must be recorded for the confirmed execution Hardware and systems?
- What fields and interaction model define a Verification Request from an engineer, team workflow, or FLAIR?
- What Capability taxonomy and Environment Registry map user verification Requirements to feasible real execution?
- Which request values may PROVE derive or default, and which missing or conflicting values require user intervention?
- What exact repository revisions become the August 2026 legacy baselines?
- Which Git repository is canonical for Gate Baseline manifests and protected tags?
- What naming, approval, retention, and correction policy applies to Main and Deri Gate Baselines?
- What Package Manifest contract references official Test Versions outside formal Gate Baselines?

# SkyTower and Integrations

- What are SkyTower's current internal agents, services, data models, and responsibilities?
- What PROVE-facing API replaces or adapts its current heavy interface?
- What API and ownership agreement is available for the downstream failure system?
- Can PROVE modify the internal Spec RAG, or only query it?
- What are the FLAIR input and feedback contracts?
- What are the PROVE-to-BRAIN handoff and BRAIN feedback contracts?

# Failure Governance

- What schema and lifecycle states define a Failure Analysis Record?
- How are similar Failure occurrences clustered without losing individual Evidence and lineage?
- What confidence or evidence threshold permits autonomous disposition?
- What Evidence is sufficient to consider each plausible Non-device cause reasonably excluded rather than merely unobservable?
- Who is accountable for incorrect PROVE classifications?
- What repair, recovery, and retry limits apply?
- What exact report schema accompanies handoff or human escalation?

# Knowledge and Organization

- Who owns Workstreams 1 through 7 and Root Knowledge, and which reviewers accept Milestone Reviews 1 through 5 Evidence?
- What are the complete R&R, product scope, time budget, Tool boundary, and handoff rules for SWE, cSSD verification, eSSD verification, and FTE?
- How does each team's Test selection authority interact with common Coverage obligations and project-level official verdicts?
- Who owns shared identities and resolves cross-team mapping or conflict proposals?
- Which expert represents each verification team in the design of Workspace, View, selection, promotion, and conflict rules?
- What exact states, Evidence, approvers, regression checks, demotion, and revocation rules govern operational Knowledge Trust?
- Which minimum Trust State is required for official Coverage, project verdict, Test Package, and Gate Baseline use?
- Who are the accountable experts, and what quorum or approval rule applies to Project, Team, Product, Customer, and Global promotion?
- What severity and impact policy controls emergency Knowledge revocation, execution blocking, notification, and mandatory revalidation?
- Which Outputs are durable governed artifacts, and which raw events require only integrity and completeness checks?
- What Review Record schema and conditional downstream-use policy apply to each artifact type?
- Which User, Team, Project, Main/Deri, Customer, Product, and Global scope relationships are required, and how are conflicts or precedence handled?
- What offline, cache, and synchronization behavior is required for engineer-local Agent operation?

# Agent Operation

- What event schema and storage system represent Agent Workflow Runs, steps, Handoffs, checkpoints, retries, resumes, and costs?
- Which changes require a new Workflow Run, child Attempt, or Test Execution Run identity?
- Which Artifact boundaries are durable Checkpoints, and what dependency rule invalidates each downstream boundary?
- What retry, timeout, cancellation, and escalation policies apply to each Agent and execution stage?
- What equivalence criteria demonstrate preserved Scenario intent and Test quality across non-identical generated outputs?
- What retention and privacy rules apply to complete Agent inputs, outputs, intermediate reasoning artifacts, and Tool records?
- What are the precise organizational meanings of eSSD and cSSD?
- What retention and deletion policy applies to prompts, logs, and generated artifacts?
- What approval is required before customer specifications enter a commercial LLM?
- What are the final repository names and internal Git URLs?
- What shared or separate artifact representation, schema, and file boundary implement the agreed Test Case and Test Script concepts?
- How do Verification Patterns, Test Scenarios, and unified Test Library capabilities reference each other?
- What are the four- and six-month milestone outcomes?

# Resolution Rule

Every resolved question must link to an ADR or verified concept update. Do not delete historical questions without recording their resolution.

Coverage-axis questions remain open by deliberate decision, not by omission.
