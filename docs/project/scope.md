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
  - id: core-directive-2026-07-27
    resource: /sources/coverage-core-directive-2026-07-27.md
    title: PROVE leader Coverage core directive
    author: human:prove-leader
    last_modified: 2026-07-27
  - id: discovery-2026-08-02
    resource: /sources/discovery-2026-08-02.md
    title: PROVE working discovery discussion
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Current Mission Model

## Spec-to-Test Platform

Use official NVMe specifications, OCP specifications, customer specifications, and internal requirements to extract scenarios, generate tests, execute them, and analyze results.

The first verification focus is HIL. FTL policy and security-feature verification remain part of the broader domain but are not confirmed as the initial implementation scope.

## FLAIR-Integrated Verification

Use firmware policy, specifications, requirements, source context, change intent, and generated firmware artifacts from FLAIR as another input path into the shared PROVE pipeline.

## Global Test Package Convergence

Extract implicit Verification Intent and reusable engineering knowledge from more than 20,000 independently managed Tests, identify overlap and gaps, and migrate validated areas gradually. The Global Test Package is a natural result of PROVE adoption rather than a forced merge mission.

The integrated package must be evaluated for both Intent preservation and actual defect-detection preservation. Test Case count or code similarity is not sufficient evidence.

Four verification-team packages are selected as initial legacy sources. Detailed ownership, baseline commits, and migration approval remain undefined.

# Initial Focus

The initial focus is the common NVMe portion shared by eSSD and cSSD. The first input may use one or two specification types and fewer than ten features. Exact scope is not yet selected.

Firenze is the first real-project pilot. Legacy Tests remain official, and PROVE-generated Tests also contribute to official verdicts. Full PROVE use is targeted for the following project.

# Explicit Boundaries

- PROVE's goal is measurable verification capability, not delivery of a specific tool.
- Coverage axes are out of definition until verification experts approve them.
- IceT, SkyTower, languages, models, and agent frameworks may change.
- PROVE's device-failure decision is a PROVE disposition, not the final root-cause conclusion of the downstream development system.
- PROVE must not be reduced to an NVMe compliance-only tool.
- Detailed implementation of IceT, SkyTower, and other subprojects belongs in their respective repositories.
- Customer-specification transmission to a commercial LLM remains subject to NDA review.
