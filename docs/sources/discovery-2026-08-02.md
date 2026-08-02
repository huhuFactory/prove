---
type: Source Summary
title: PROVE Working Discovery Discussion — 2026-08-02
description: Dated capture of evolving project-leader thinking about missions, migration, legacy assets, integrations, and milestones.
tags: [prove, source, discovery, evolving]
status: draft
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Source Status

This is a structured summary, not a verbatim transcript or final decision. The PROVE leader explicitly stated that the working model may continue to change. Derived concepts must remain `draft` unless separately confirmed.

# Missions

- Mission 1 transforms Test Specifications into Requirements, Test Scenarios, executable Tests, real-environment execution, and complete Traceability.
- Mission 2 integrates with FLAIR so firmware-development inputs and outputs enter the same downstream PROVE pipeline.
- Test Case and Test Script terminology will be defined later.

# Global Package Migration

- Global integration is intended as natural convergence, not a forced one-time merge.
- Four verification teams and their packages are selected as legacy inputs.
- Test Scenarios are treated as primary durable assets, including embedded engineer knowledge.
- Existing packages migrate gradually over approximately six months or longer after regenerated Tests prove suitable.
- The exact initial demonstration Spec, Feature, and package subset is not selected.

# Legacy Assets

- IceT is the shared Test Platform and API abstraction across several hardware types, not one common hardware device.
- Existing Tests are JavaScript files.
- Team-specific Test Libraries and Tests live in the same Git repository and form one inseparable version unit.
- Documentation and Specification links are incomplete and inconsistent.
- Execution history, Failure analysis, and Bug information may be accessible, but no reliable Test linkage exists; reconstruction is manual or inferential.

# Adoption

- Firenze is the first real-project PROVE pilot.
- Firenze continues official legacy IceT and Test Package use.
- PROVE-generated Tests also contribute to official Pass/Fail decisions.
- Full PROVE use is targeted for the project after Firenze rather than Firenze itself.

# FLAIR and BRAIN

- FLAIR develops SSD firmware through AI Agents and Vibe Coding.
- PROVE classifies Failure as device or non-device.
- Device failures are handed automatically to BRAIN without human approval.
- BRAIN AI Agents automatically perform deeper firmware-failure analysis.
- A future FLAIR–PROVE–BRAIN closed loop is desired but is not committed within two months.

# Milestones

- Three horizons are planned: two, four, and six months.
- The first two weeks prioritize an operationally applicable Coverage method and system for leadership agreement.
- Coverage is intended to guide Requirement-to-Scenario derivation, not only report results afterward.
- The required two-month outcome reaches generation, real execution, Traceability, Pass/Fail, and device/non-device disposition.
- Automatic BRAIN handoff and analysis is a two-month stretch goal dependent on external support.
- Four- and six-month content remains open.
