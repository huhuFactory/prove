---
type: Source Summary
title: Agent Run Hierarchy Directive — 2026-08-02
description: Confirmation of PROVE request, Agent workflow, Hardware execution, retry, and Failure analysis trace units.
tags: [prove, source, agent, workflow-run, execution-run, traceability]
status: stable
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
verified: { by: "human:prove-leader", at: "2026-08-02T00:00:00+09:00" }
---

# Confirmed Direction

- A versioned Verification Request is the parent unit for one or more Agent Workflow Runs.
- An Agent Workflow Run records one processing attempt, including Agent steps, handoffs, generated artifacts, retries, and one or more Test Execution Runs.
- A Test Execution Run records one real-Hardware execution attempt.
- A failed Test Execution Run may create a Failure Analysis Record that traces subsequent analysis and action.
- Retry, resume, regeneration, and re-execution must not overwrite prior attempts; they create new identities linked to their parent and predecessor.
- Reprocessing with a different Model, Prompt, Knowledge, Tool, or Workflow version creates a separately traceable Workflow Run.
- PROVE reproducibility does not require an LLM to generate byte-identical text or code for every repeated input.
- Reproducibility combines complete audit reconstruction, operational replay when pinned dependencies remain available, and evaluation of equivalent verification intent and quality.
- Deterministic identity or byte equivalence may still be required for artifacts and steps whose contracts explicitly require it.
- Agent Handoffs use versioned Artifacts, their identities, and Evidence rather than relying only on conversational summaries.
- Major durable Artifact boundaries provide Checkpoints for interruption and recovery.
- Resume creates a new linked Attempt from the last still-valid Checkpoint and does not overwrite the interrupted Run.
- If an upstream Source, input, or Artifact changed, PROVE invalidates affected downstream Checkpoints and recomputes from the earliest impacted boundary.
- Retry is bounded and records its cause, policy, result, and escalation; exact limits remain to be defined.
