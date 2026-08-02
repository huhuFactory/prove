---
type: Governance
title: Artifact Lifecycle and Governance
description: Cross-cutting rules requiring explicit Inputs, versioned Outputs, Evidence-based Review, lifecycle control, and complete Traceability for every durable PROVE artifact.
tags: [prove, governance, artifact, input, output, review, traceability]
status: draft
sources:
  - id: generated-artifact-governance-directive-2026-08-02
    resource: /sources/generated-artifact-governance-directive-2026-08-02.md
    title: Generated Artifact Governance priority directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Priority

Test Scenario extraction produces PROVE's most important long-term asset. Governance of that Scenario and every later generated artifact is the next priority. PROVE must not scale Test generation before it can identify, version, review, trace, correct, and revoke the resulting artifacts.

A minimum identity and provenance envelope also applies from the first Source and Requirement stage. Priority after Scenario extraction means completing and enforcing the Governance capability before downstream generation expands; it does not permit earlier artifacts to be untraceable.

# Mandatory Stage Contract

Every durable PROVE stage Output that feeds a downstream decision, execution, or official claim follows the same control pattern:

```text
Versioned Inputs
→ versioned Producer and processing contract
→ immutable Output version
→ Evidence-based Output Review
→ accepted, conditionally accepted, or rejected Review Record
→ accepted Output becomes a downstream Input
```

Review does not always mean manual approval. It may be automated, Agent-based, expert-based, or combined, but the reviewer, criteria version, Evidence, decision, limitations, and time must be recorded. Raw events and raw Evidence may use integrity and completeness checks rather than semantic acceptance. The exact durable-output boundary and review authority for each artifact type cannot yet be decided.

# Governed Artifacts

The rule applies at least to:

- Verification Request and resolved context
- Source registration and extracted Requirement
- Verification Knowledge and Verification Pattern
- Source Scenario Candidate, Canonical Scenario, and Scenario Variant
- Verification Space representation, Coverage computation, Gap, and evaluation result
- Test Case, Test Script, Oracle, configuration, and Test Version
- Execution Plan, environment resolution, and applicability decision
- Agent Workflow Run, Handoff, Checkpoint, and generated Artifact
- Test Execution Run, raw and interpreted Evidence, and Test Verdict
- Failure Analysis Record, Disposition, repair, recovery, and BRAIN Handoff Package
- Package Manifest, Gate Baseline Manifest, and promotion or Revocation decision

This list is a minimum working set. Whether additional artifact types are required cannot yet be decided.

# Minimum Artifact Record

Every governed Output must be able to reference:

- Stable artifact identity, type, and immutable Version
- Parent Verification Request and applicable Source or Baseline
- Exact Input artifact Versions
- Producer identity and Agent Workflow Run
- Content identity or digest
- Applicability Scope and known exclusions
- Current lifecycle or Trust state appropriate to its artifact type
- Validation and execution Evidence
- Review Record and unresolved conditions
- Downstream consumers and impact relationships
- Supersession, deprecation, Revocation, and correction lineage

The physical schema, database technology, identifier format, and universal field cardinality cannot yet be decided.

# Output Review Record

Every Review produces its own versioned Output containing:

- Reviewed artifact and Version
- Review type and criteria Version
- Reviewer or evaluating system identity
- Evidence examined
- Accepted, conditionally accepted, or rejected decision
- Conditions, Gaps, uncertainty, and required follow-up
- Applicable scope and expiration or re-review trigger when known
- Review time and predecessor Review

An Output without a Review Record may remain experimental. It must not silently become an official downstream Input.

# Change and Invalidity

Changing an Input or processing contract creates a new Output Version or invalidates the affected downstream Review. Incorrect artifacts are revoked rather than deleted. Traceability identifies affected Requirements, Scenarios, Cases, Coverage claims, Runs, verdicts, Packages, and Baselines for re-review or revalidation.

# Cannot Yet Be Decided

The following details are intentionally unresolved:

- One universal lifecycle shared by every artifact type
- Exact mandatory metadata schema and storage implementation
- Review authority and quorum for every artifact and applicability scope
- Automated versus human Review boundaries
- Acceptance thresholds, expiration periods, and re-review frequency
- Emergency Revocation authority and notification policy
- Which conditional Reviews may feed which official downstream stages

These decisions require Workstream owners, verification-team experts, and Evidence from the first operational slice.
