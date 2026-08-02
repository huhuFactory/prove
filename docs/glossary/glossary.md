---
type: Glossary
title: PROVE Glossary
description: Shared vocabulary for PROVE and its subprojects.
tags: [prove, glossary, terminology]
status: draft
sources:
  - id: discovery-2026-07-26
    resource: /sources/discovery-interview-2026-07-26.md
    title: PROVE leader discovery discussion
    author: human:prove-leader
    last_modified: 2026-07-26
  - id: discovery-2026-08-02
    resource: /sources/discovery-2026-08-02.md
    title: PROVE working discovery discussion
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Terms

| Term | Working definition |
|---|---|
| PROVE | AI-based SSD verification initiative spanning test generation, execution, analysis, package integration, and firmware-development feedback. |
| DUT | SSD device under test. |
| HIL | Host Interface Layer verification covering externally visible protocol and specification behavior. |
| FTL | Verification of internal firmware policies and behavior associated with the Flash Translation Layer. |
| Security Feature | SSD security capability such as SPDM and related policies. |
| IceT | Existing internal SSD Test Platform. Its future form is expected to retain a resilient low-level core while reducing feature-specific high-level APIs. |
| SkyTower | Internal large-scale validation automation infrastructure containing multiple agents and services. Detailed structure is pending. |
| FLAIR | AI Agent and Vibe Coding-based SSD firmware development project that supplies development context to PROVE. Detailed contracts are pending. |
| BRAIN | AI Agent-based SSD firmware Failure analysis project that receives device failures from PROVE. |
| Firenze | First real-project PROVE pilot. Legacy and PROVE Tests both contribute to official verification. |
| Test Design | Activity that transforms test conditions, Requirements, Coverage needs, Patterns, and risk into specified Scenarios and Cases. Proposed PROVE definition. |
| Test Scenario | PROVE's most important long-term asset: an implementation-independent definition of verification intent and the meaningful verification space to explore. |
| Source Scenario Candidate | A Scenario interpretation extracted from one versioned Source and preserved before or after canonical mapping. |
| Canonical Scenario | Shared verification intent to which one or more Source Scenario Candidates are traceably mapped without replacing them. Its catalog hierarchy is not yet approved. |
| Scenario Variant | A traceable specialization of shared Scenario intent for a meaningful product, customer, policy, state, or condition difference. |
| Test Case | A concrete, traceable selection of states, paths, conditions, and parameters intended to fill part of a Scenario-defined verification space. |
| Test Script | Replaceable executable implementation of a Test Case for a particular language, runtime, and API contract. |
| State Contract | Declaration of the Pre-State a Test Case requires, the state changes it may cause, its expected Post-State, and its cleanup or preservation policy. The detailed schema is not yet approved. |
| Sequence-dependent Failure | Failure observed in a later Test Case whose necessary causal or activating state may have been created by one or more earlier Cases. |
| Verification Baseline | Immutable, approved manifest of exact Source, Knowledge, Scenario, Case, firmware, and execution-contract version references used at a formal project Gate. |
| Working View | Continuously changing set of current verification inputs and assets from which a Gate Baseline may later be frozen. |
| Run Manifest | Automatically captured record of the exact versions, environment, parameters, and artifacts actually used by one Test execution. |
| Verification Pattern | Reusable, implementation-independent engineering knowledge applied by one or more Scenarios and implemented by Test Library capabilities. Proposed definition. |
| Test Library | Package-local JavaScript library that composes IceT APIs into reusable team-specific behavior. It is versioned with and inseparable from its Test Package. |
| Test Package | A managed collection of Test Cases owned by a site or team. |
| Global Test Package | Long-term converged package produced through gradual validated PROVE migration, not a forced one-time merge. |
| Coverage | Degree to which a defined verification space is exercised. The dimensions and computation method are not yet approved. |
| Bidirectional Traceability | Ability to navigate both from a Source to every derived verification and result asset and from any result back to all Sources, transformations, decisions, and versions. |
| Platform Invariant | Condition IceT must satisfy across every technically supported Test, including retention of execution control and Evidence through Reset, Error, and abnormal Device states. |
| Verification Request | Versioned expression of what a user or approved upstream system needs PROVE to verify, including its project and execution context. The exact schema is not yet approved. |
| Applicability | Ability to map a Verification Request to valid Requirements, Scenarios, Cases, and a feasible real execution environment while exposing unmet conditions. |
| Execution Plan | Traceable resolution of selected Tests, environments, constraints, order, and configuration for a Verification Request. The exact schema is not yet approved. |
| Test Verdict | Execution-level Pass or Fail result produced by comparing observed behavior with a Test Oracle. It is separate from Failure Disposition. |
| Failure Disposition | PROVE's evidence-based classification of a Test Failure as Device, Non-device, or Unknown after the Test Verdict. |
| Failure Analysis Agent | Logical Agent capability within PROVE that is triggered by a Test Fail and determines Failure Disposition and follow-up action. It is distinct from BRAIN. |
| Failure Analysis Record | Stable, versioned Traceability record for one observed Test Fail spanning first Evidence, reproduction, analysis, Disposition, repair or recovery, rerun, BRAIN exchange, and closure. |
| Agent Workflow Run | One immutable processing Attempt of a Verification Request through versioned Agents, Prompts, Models, Knowledge, Tools, Handoffs, and generated Artifacts. |
| Test Execution Run | One immutable attempt to execute a Test on real Hardware with exact DUT, FW, Platform, environment, configuration, Evidence, and verdict references. |
| Official Test Version | Validated Test Case Version referenced by an applicable official Package or Gate Baseline Manifest. Officiality is determined by that Manifest context rather than a global state on the Test. |
| Workstream | Continuous body of related work with an accountable owner, deliverables, dependencies, and completion Evidence. A Workstream is not necessarily one Agent or repository. |
| Milestone Review | Evidence review point that accepts, conditionally accepts, or returns a bounded outcome for revision. It organizes the PROVE plan and does not replace company WS or ES development Gates. |
| Governed Artifact | Versioned PROVE Input, Output, Evidence, decision, or manifest with identity, provenance, Review, lifecycle, downstream use, and correction or Revocation lineage. |
| Review Record | Versioned Output of an artifact Review containing criteria, reviewer, Evidence, decision, conditions, uncertainty, scope, and follow-up. |
| Knowledge Applicability Scope | Independent set of User, Team, Project, Main/Deri, Customer, Product, Global, version, and condition contexts in which a Verification Knowledge item may be used. It is not a quality rank. |
| Knowledge Trust State | Operational maturity of a Verification Knowledge item, provisionally Draft, Candidate, Validated, Verified, or Deprecated. It is separate from OKF document status. |
| 진성 Fail / Device Failure | Failure where the SSD product does not perform its defined behavior from the host perspective. Includes any underlying SSD FW, HW, media, manufacturing, quality, performance, or conformance cause. |
| 가성 Fail / Non-device Failure | Failure caused by anything other than the SSD device, including Test Case, platform, infrastructure, host, environment, configuration, or interpretation. |
| Unknown | Failure state that PROVE cannot classify with sufficient evidence and must escalate to a person. |
| SSD Verification Specification | Working concept for the capabilities and behavior required of the Test Platform. It is broader than the NVMe specification and has not yet been formalized. |
| eSSD / cSSD | Internal SSD product-family terms. Their expanded names and precise organizational definitions must be confirmed internally. |

# Usage Rule

Subprojects must reuse these meanings. A project-specific extension is allowed, but a conflicting definition requires a Root Knowledge change proposal.
