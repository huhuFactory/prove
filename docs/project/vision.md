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
  - id: core-directive-2026-07-27
    resource: /sources/coverage-core-directive-2026-07-27.md
    title: PROVE leader Coverage core directive
    author: human:prove-leader
    last_modified: 2026-07-27
generated: { by: openai-codex/gpt-5, at: "2026-07-27T00:00:00+09:00" }
---

# Vision

PROVE structures accumulated SSD verification knowledge so AI agents can create better and broader tests, measure the verification capability they preserve or add, execute them against real devices, and analyze failures with traceable evidence.

# Core Value

PROVE must preserve and expand both engineering Verification Intent and actual defect-detection capability. Defining a defensible verification space and Coverage method is part of the product, not a reporting task added after Test Case generation.

See [PROVE Core Value](/principles/core-value.md).

# Mission

Build an internal platform that can:

1. Interpret NVMe, OCP, customer, and internal requirements.
2. Extract test scenarios and generate executable test cases.
3. Extract reusable Verification Knowledge from existing Test Cases and failure experience.
4. Measure preservation, loss, and expansion of verification capability.
5. Execute tests through adaptable execution and automation tools.
6. Distinguish SSD-device failures from non-device failures.
7. Repair recoverable test or environment failures and repeat execution.
8. Integrate independently developed test packages into a global package.
9. Generate and execute tests alongside AI-assisted SSD firmware development.

# North-Star Outcome

A specification, engineering policy, firmware artifact, or existing test package can enter PROVE and produce a reproducible chain from source knowledge to Verification Intent, scenario, test code, Coverage evidence, execution evidence, and failure disposition.

# Important Boundary

PROVE verifies SSD devices. NVMe specification conformance is one verification category, not the complete purpose of the platform.

IceT, SkyTower, languages, models, and agent frameworks are replaceable means. They must not redefine the project goal.
