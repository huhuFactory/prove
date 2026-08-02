---
type: Source Summary
title: PROVE Failure Analysis Agent Directive — 2026-08-02
description: Confirmation that Test Verdict and Failure Disposition are separate states and a PROVE Agent analyzes every Test Fail.
tags: [prove, source, failure-analysis, agent, disposition]
status: stable
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
verified: { by: "human:prove-leader", at: "2026-08-02T00:00:00+09:00" }
---

# Confirmed Direction

- Test Pass/Fail and Failure Device/Non-device/Unknown Disposition are separate lifecycle states.
- A Test Fail triggers a Failure Analysis Agent within PROVE.
- The PROVE Failure Analysis Agent analyzes Evidence and determines whether the Failure is Device, Non-device, or Unknown.
- BRAIN is not the PROVE Failure Analysis Agent. BRAIN is the downstream system invoked after PROVE reaches a Device Failure Disposition.
- PROVE must preserve the first-Failure Evidence before Reset, recovery, rerun, or other analysis changes the state.
- Reproduction is planned adaptively by the Failure Analysis Agent rather than imposed as one mandatory identical procedure for every Failure.
- Reproduction attempts, outcomes, omissions, and rationale are Evidence.
- A Failure remains Unknown when reproduction and other analysis do not provide sufficient grounds for Device or Non-device Disposition.
- Each observed Test Fail creates a stable Failure Analysis Record that traces the initial occurrence through analysis, disposition, action, rerun, BRAIN handoff, and returned feedback.
- Individual Failure occurrences remain preserved even when they appear similar. Later clustering may relate them without destructively merging their records.
- PROVE may reach a Device Failure Disposition through direct Device Evidence or by reasonably excluding Test, IceT, Host, environment, configuration, and other Non-device causes while a defined Device-behavior violation remains.
- PROVE does not need to establish the internal SSD root cause before handing a Device Failure to BRAIN.
- Failure to find a Non-device cause after adequate analysis differs from inability to analyze that cause. The former may support Device Disposition; the latter remains Unknown when Evidence is insufficient.
