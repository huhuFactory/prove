---
type: Organization Model
title: Verification Team R&R
description: Separately maintained facts about the roles, scopes, constraints, and handoffs of verification organizations using PROVE.
tags: [prove, organization, r-and-r, swe, fte, essd, cssd]
status: draft
sources:
  - id: verification-organization-and-selection-directive-2026-08-02
    resource: /sources/verification-organization-and-selection-directive-2026-08-02.md
    title: Verification organization and Test selection directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Purpose

This page records organization-specific R&R separately from PROVE architecture and common Test rules. Each verification team must review and complete its own profile. Unconfirmed details remain explicit rather than being inferred.

# Current Profiles

## Headquarters SWE

- Organization: FW organization
- Product scope: eSSD only at present
- Verification scope: FW-focused verification
- Time budget: guaranteed 48 hours
- Input, selection authority, handoff, Tool, Hardware, and official-verdict responsibilities: confirmation required

## Headquarters cSSD Verification Team

- Product scope: cSSD only
- Verification scope: whole-device DVT
- Primary Platform: IceT, approximately 90–95% or more; exact figure requires confirmation
- Other Tools: performance and power-consumption areas that IceT cannot verify
- Distinguishing scope: low-power verification using IceT
- Hardware: cSSD-specific verification Hardware controlled through IceT
- Time budget, input, selection authority, handoff, and official-verdict responsibilities: confirmation required

## Headquarters eSSD Verification Team

- Product scope: eSSD only
- Verification scope: whole-device DVT
- Primary Platform: IceT, approximately 95% or more; exact figure requires confirmation
- Hardware: eSSD-specific verification Hardware controlled through IceT
- Input characteristics: extensive customer Requirements, customer-requested OCP versions, TP support, and different Specification obligations across Main and Deri projects
- Time budget, selection authority, handoff, other Tool boundary, and official-verdict responsibilities: confirmation required

## United States Development Branch FTE

- Organization: FW organization in the United States development branch
- Verification scope: FW-focused verification
- Time budget: usually 24 hours
- Handoff: passing results are transferred to another team for additional Test execution
- Relationship: role is similar to SWE; exact similarities and differences require confirmation
- Product scope, input, selection authority, Tool, Hardware, receiving organization, and official-verdict responsibilities: confirmation required

# Team Review Request

Each organization should complete a profile using [Verification Team R&R Template](/templates/verification-team-r-and-r.md). The team reviewer must distinguish current facts from desired future PROVE operation and identify the effective project or Gate when a rule changes.

# Boundary

This page explains who verifies what and under which constraints. Common PROVE architecture, Knowledge identity, Traceability, Test qualification, and lifecycle rules belong in their respective Root concepts and must not be redefined independently in a team profile.
