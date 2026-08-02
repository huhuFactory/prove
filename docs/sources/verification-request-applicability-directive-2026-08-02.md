---
type: Source Summary
title: Verification Request Applicability Directive — 2026-08-02
description: Confirmation that Applicability maps user verification requirements to executable Tests and real environments rather than merely matching Tests to Hardware.
tags: [prove, source, applicability, verification-request, execution]
status: stable
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
verified: { by: "human:prove-leader", at: "2026-08-02T00:00:00+09:00" }
---

# Confirmed Direction

- Applicability starts from the user's verification Requirements.
- PROVE must map those Requirements to executable Tests and real execution environments.
- Applicability is not merely a Test-to-Hardware matching function.
- Environment selection is performed by an execution Agent, but must remain grounded in the originating user, project, product, Specification, and verification context.
- The mapping from the request through selected verification assets and environment must be traceable.
- User input may arrive in different forms, but PROVE must normalize it into a versioned Verification Request before generation and execution.
- The Verification Request is the top-level Traceability unit for all derived Requirements, Scenarios, Cases, Execution Plans, runs, Evidence, and verdicts.
