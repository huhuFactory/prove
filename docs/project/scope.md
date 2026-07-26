---
type: Scope
title: PROVE Scope and Boundaries
description: Current in-scope workstreams, initial focus, and explicit boundaries.
tags: [prove, scope, hil, test-package, firmware]
status: draft
sources:
  - id: discovery-2026-07-26
    resource: /sources/discovery-interview-2026-07-26.md
    title: PROVE leader discovery discussion
    author: human:prove-leader
    last_modified: 2026-07-26
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Workstreams

## Spec-to-Test Platform

Use official NVMe specifications, OCP specifications, customer specifications, and internal requirements to extract scenarios, generate tests, execute them, and analyze results.

The first verification focus is HIL. FTL policy and security-feature verification remain part of the broader domain but are not confirmed as the initial implementation scope.

## Global Test Package Integration

Extract intent and scenarios from more than 20,000 independently managed test cases, identify overlap and gaps, rewrite tests for the common platform, and produce a global package.

Independent owners may be different sites or different teams within one site. Ownership, approval, and migration policy remain undefined.

## Firmware Development Integration

Use SRS, firmware policy, generated code, and code changes to generate and execute relevant tests at the firmware developer's workstation, then feed results back into development.

# Initial Focus

The initial focus is the common NVMe portion shared by eSSD and cSSD. The first input may use one or two specification types and fewer than ten features. Exact scope is not yet selected.

# Explicit Boundaries

- PROVE's device-failure decision is a PROVE disposition, not the final root-cause conclusion of the downstream development system.
- PROVE must not be reduced to an NVMe compliance-only tool.
- Detailed implementation of IceT, SkyTower, and other subprojects belongs in their respective repositories.
- Customer-specification transmission to a commercial LLM remains subject to NDA review.
