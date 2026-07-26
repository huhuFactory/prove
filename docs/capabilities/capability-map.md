---
type: Capability Map
title: PROVE Capability Map
description: Logical capabilities and candidate subproject ownership boundaries.
tags: [prove, capabilities, subprojects]
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

# Core and Enabling Capabilities

Verification Knowledge and measurable Coverage are the core. Test generation, IceT, SkyTower, and other infrastructure enable that core and remain replaceable.

# Capability Map

| Capability | Responsibility | Candidate owning project |
|---|---|---|
| Knowledge ingestion | Access, parse, and version specifications, policies, SRS, code context, and existing tests | Scenario/knowledge project |
| Verification knowledge extraction | Recover implicit Intent and reusable engineering knowledge from existing tests and failure experience | Knowledge/Coverage project |
| Requirement modeling | Represent requirements, precedence, conditions, and evidence | Scenario extraction |
| Scenario extraction | Produce traceable verification scenarios | Scenario extraction |
| Test generation | Produce executable code, parameters, expected results, and cleanup | Test generation |
| Quality and Coverage | Define verification space and measure generated tests | Coverage/evaluation project |
| Capability equivalence | Independently evaluate Intent preservation and defect-detection preservation | Coverage/evaluation project |
| Test execution | Build and execute low-level SSD verification logic | IceT |
| Device control | Command, reset, power, sideband, memory, and error-injection control | IceT |
| Workflow orchestration | Coordinate agents and execution backends | SkyTower/PROVE workflow |
| Mass execution | Allocate, schedule, observe, and collect large-scale runs | SkyTower |
| Failure analysis | Reproduce, classify, explain, and select follow-up action | Failure analysis |
| Repair loop | Modify Test Cases or recover environments, validate, and rerun | Cross-project workflow |
| Package governance | Version, validate, approve, and distribute Test Cases | Global package |
| Firmware feedback | Generate and execute tests from SRS, policy, code, and changes | FW integration |
| Knowledge governance | Maintain shared definitions, decisions, and provenance | PROVE Root Knowledge |

# Boundary Status

Repository boundaries and names are proposals. Each capability must have one accountable owner, even when several projects collaborate.

# Cross-Cutting Contracts

- Shared identifiers for requirements, scenarios, tests, runs, failures, and artifacts
- Common execution request and result contracts
- Versioned evidence and lineage
- Failure disposition and feedback contracts
- Root Knowledge version pinning
