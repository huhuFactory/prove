---
type: Roadmap
title: PROVE Directional Roadmap
description: Outcome-oriented stages for PROVE without committing unapproved dates or scope.
tags: [prove, roadmap, milestones]
status: draft
sources:
  - id: discovery-2026-07-26
    resource: /sources/discovery-interview-2026-07-26.md
    title: PROVE leader discovery discussion
    author: human:prove-leader
    last_modified: 2026-07-26
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Roadmap Principles

Stages are governed by exit evidence rather than dates alone. Work may proceed in parallel after interfaces and evaluation criteria are agreed.

# Directional Stages

## Foundation

- Approve the charter, glossary, knowledge governance, and capability boundaries.
- Select initial specifications and features.
- Define Test Case quality and Coverage hypotheses.
- Establish representative expert-authored evaluation evidence.

## Thin End-to-End Validation

- Extract scenarios from one or two specification types.
- Generate executable tests for fewer than ten features.
- Run tests on an engineer-assigned execution system.
- Preserve requirement-to-result traceability.
- Demonstrate an initial Coverage measurement.

The current internal demonstration target is 2026-08-27.

## Execution Platform and Workflow

- Establish the AI-native IceT core direction.
- Define a C++-oriented Test Case contract or select another language through an explicit decision.
- Connect local execution and SkyTower through a common workflow boundary.
- Preserve control across reset, power, recovery, and error-injection paths.

## Failure Analysis Loop

- Classify failures as device, non-device, or unknown.
- Handoff device failures with evidence.
- Repair or recover non-device failures, revalidate changes, and rerun.
- Capture downstream corrections as feedback.

## Scale and Expansion

- Expand specification and feature coverage.
- Integrate global test packages.
- Connect SRS, firmware policy, and code-change workflows.
- Operate across large-scale SkyTower environments.

# Date Status

An initial result is desired around 2026-09-30. TF duration may be extended after the plan and evidence are reviewed.
