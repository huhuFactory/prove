---
type: Source Summary
title: Verification Organization and Test Selection Directive — 2026-08-02
description: Confirmed organizational context and team-owned selection of executable Test candidates.
tags: [prove, source, organization, test-selection, swe, fte, essd, cssd]
status: stable
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
verified: { by: "human:prove-leader", at: "2026-08-02T00:00:00+09:00" }
---

# Confirmed Selection Direction

- Each verification team should select the Test Case candidates it will execute because team R&R, product scope, verification purpose, time budget, Hardware, and Tools differ.
- PROVE must not assume that one centrally fixed execution list is equally applicable to every verification team.
- Selection ownership does not remove the need for common Scenario, Case, Coverage, Traceability, and execution Evidence.
- PROVE is one common system rather than independent PROVE instances owned by each verification team.
- The common system uses a shared logical Knowledge and Traceability plane while supporting team- and project-specific use.
- Detailed operation must be defined later with domain experts representing each verification team.

# Known Verification Organizations

## Headquarters — SWE

- Belongs to the FW organization and performs FW-focused verification.
- Has a guaranteed verification duration of 48 hours.
- Currently handles eSSD verification only.

## Headquarters — cSSD Verification Team

- Focuses only on cSSD verification.
- Covers the whole Device through DVT, meaning Device Verification.
- Uses IceT for approximately 90–95% or more of verification.
- Uses separate Tools only for areas IceT cannot verify, including performance and power consumption.
- Low-power Test execution using IceT is a major difference from eSSD verification.
- Uses cSSD-specific verification Hardware controlled through IceT.

## Headquarters — eSSD Verification Team

- Focuses only on eSSD verification.
- Covers the whole Device through DVT.
- Uses IceT for approximately 95% or more of verification; the exact figure is not yet confirmed.
- Operates eSSD-specific verification Hardware separately from cSSD Hardware, with both controlled through IceT.
- Must handle extensive and diverse customer Requirements.
- Main and Deri projects may each support different customer Specifications and explicitly requested OCP versions.
- Technical Proposal, or TP, support requests are common and add project-specific verification input.

## United States Development Branch — FTE

- Separate verification team in the United States branch and belongs to the FW organization.
- Performs FW-focused verification.
- Usually operates with a relatively short 24-hour verification duration.
- Transfers a passing result to another team for additional Test execution.
- Its role is similar to SWE, subject to later clarification of the differences.

# Explicit Unknowns

- SWE and FTE expanded names are not recorded.
- Exact eSSD and cSSD IceT usage percentages are not confirmed.
- Selection authority, review, and conflict rules inside each team are not yet defined.

# Deployment Concern

- Multiple verification teams will continuously submit Specifications, Requirements, Scenarios, Cases, and engineering knowledge to PROVE.
- PROVE must preserve complete Traceability while supporting different team R&R and project contexts.
- Managing these concurrent inputs and presenting the appropriate verification view to each team is a central deployment concern.
