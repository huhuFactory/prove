---
type: Source Summary
title: PROVE Leader Discovery Discussion — 2026-07-26
description: Structured capture of facts and intentions provided by the PROVE leader before work resumed inside the company.
tags: [prove, source, discovery]
status: draft
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Source Context

This document summarizes a direct conversation with the PROVE TF leader. It is not a verbatim transcript. It must be reviewed against internal facts after the repository is moved into the company environment.

# Project Intent

- Generate SSD Test Scenarios and Test Cases from NVMe, OCP, customer, and internal specifications.
- Execute generated tests and analyze failures.
- Decide whether a failure is caused by the SSD device.
- Integrate more than 20,000 independently managed Test Cases into a global package.
- Generate and execute tests alongside AI-assisted firmware development.
- Start with common HIL verification for eSSD and cSSD.

# Timing

- Planned TF start: 2026-07-30
- Initial reporting period: about two months, with weekly reporting
- Desired first demonstration: 2026-08-27
- Desired initial result: around 2026-09-30
- Duration can change after planning

# Team

- Eight members at an expected 80–90% effective allocation
- Five test experts: four senior eSSD experts and one cSSD engineer
- Three platform specialists: IceT/platform and TF leader, AI/platform expert, and SkyTower/backend expert
- Workstream ownership remains unassigned

# Initial Demonstration Direction

- One or two specification types
- Fewer than ten features
- Thin end-to-end flow through scenario extraction, Test Case generation, execution, and Coverage measurement
- Exact feature, specification version, RAG use, and Coverage method are unknown

# Platform Intent

- Existing IceT is JS-based and exposes many feature-specific high-level APIs.
- The proposed direction removes upper layers, retains a robust core, and exposes abstract command transfer.
- AI-generated Test Cases implement detailed feature behavior.
- C++ is currently favored because of performance, JS async usability, Node.js, and long-term third-party dependency problems.
- No C++ runtime or binding currently exists.
- IceT must retain control through all reset types and adverse verification behavior.
- IceT provides broad low-level control except direct PCIe TLP generation.
- Internal sideband and driver technology supports GPIO, power, I2C/I3C, memory mapping, and error injection.
- Existing automatic recovery is available.

# Automation and Failure Handling

- Engineer development should remain compatible with SkyTower rather than form a separate first-stage product.
- Engineer-assigned Mass-style systems are expected but not requested yet.
- SkyTower APIs exist but likely require PROVE-specific adaptation.
- The target workflow is autonomous and framework-independent.
- Device failure means any SSD product failure from the host perspective.
- Non-device failure includes Test Case, platform, host, environment, configuration, and other causes outside the SSD.
- Non-device causes are repaired or recovered, validated, and rerun.
- Unknown or unrecoverable cases request human intervention.
- Device failures are transferred to an existing downstream system; corrections return to PROVE.
- Historical data exists in SkyTower at large scale but lacks connected lineage.

# Data and Security

- Commercial LLM use is approved for internal specifications, Test Cases, logs, and FW information.
- Customer-specification use remains under NDA discussion.
- Codex is the preferred external LLM.
- A company-specific OpenAI environment is planned.
- An on-premises model exists but requires investigation.
- Spec RAG read access exists; change access is unknown.
- Long-term prompt, response, code, and log retention is allowed; TF policy is not yet defined.
