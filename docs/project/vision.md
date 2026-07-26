---
type: Project Vision
title: PROVE Vision
description: North-star purpose and intended outcome of PROVE.
tags: [prove, vision, ssd, ai, verification]
status: draft
sources:
  - id: discovery-2026-07-26
    resource: /sources/discovery-interview-2026-07-26.md
    title: PROVE leader discovery discussion
    author: human:prove-leader
    last_modified: 2026-07-26
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Vision

PROVE enables AI agents to transform SSD verification knowledge into executable tests, run those tests against real devices, and analyze failures with traceable evidence.

# Mission

Build an internal platform that can:

1. Interpret NVMe, OCP, customer, and internal requirements.
2. Extract test scenarios and generate executable test cases.
3. Measure the quality and coverage of generated tests.
4. Execute tests through IceT and automation infrastructure.
5. distinguish SSD-device failures from non-device failures.
6. Repair recoverable test or environment failures and repeat execution.
7. Integrate independently developed test packages into a global package.
8. Generate and execute tests alongside AI-assisted SSD firmware development.

# North-Star Outcome

A specification, engineering policy, firmware artifact, or existing test package can enter PROVE and produce a reproducible chain from source requirement to scenario, test code, execution evidence, and failure disposition.

# Important Boundary

PROVE verifies SSD devices. NVMe specification conformance is one verification category, not the complete purpose of the platform.
