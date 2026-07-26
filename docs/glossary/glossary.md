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
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
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
| Test Scenario | Technology- and implementation-aware statement of what behavior, condition, transition, or failure path must be verified. |
| Test Case | Executable realization of a Test Scenario, including setup, actions, parameters, expected results, evidence, and cleanup or recovery. |
| Test Package | A managed collection of Test Cases owned by a site or team. |
| Global Test Package | Intended unified package produced from independently managed test packages. |
| Coverage | Degree to which a defined verification space is exercised. The dimensions and computation method are not yet approved. |
| 진성 Fail / Device Failure | Failure where the SSD product does not perform its defined behavior from the host perspective. Includes any underlying SSD FW, HW, media, manufacturing, quality, performance, or conformance cause. |
| 가성 Fail / Non-device Failure | Failure caused by anything other than the SSD device, including Test Case, platform, infrastructure, host, environment, configuration, or interpretation. |
| Unknown | Failure state that PROVE cannot classify with sufficient evidence and must escalate to a person. |
| SSD Verification Specification | Working concept for the capabilities and behavior required of the Test Platform. It is broader than the NVMe specification and has not yet been formalized. |
| eSSD / cSSD | Internal SSD product-family terms. Their expanded names and precise organizational definitions must be confirmed internally. |

# Usage Rule

Subprojects must reuse these meanings. A project-specific extension is allowed, but a conflicting definition requires a Root Knowledge change proposal.
