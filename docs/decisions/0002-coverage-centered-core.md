---
type: Architecture Decision
title: "ADR-0002: Make verification knowledge and measurable Coverage the PROVE core"
description: Decision that tools remain replaceable while Coverage and verification capability define project success.
tags: [prove, adr, coverage, core]
status: stable
sources:
  - id: core-directive-2026-07-27
    resource: /sources/coverage-core-directive-2026-07-27.md
    title: PROVE leader Coverage core directive
    author: human:prove-leader
    last_modified: 2026-07-27
generated: { by: openai-codex/gpt-5, at: "2026-07-27T00:00:00+09:00" }
verified: { by: "human:prove-leader", at: "2026-07-27T00:00:00+09:00" }
---

# Status

Accepted by the PROVE leader on 2026-07-27.

# Context

AI Test Case generation is expected to be technically achievable. The harder project problem is proving that generated or consolidated tests preserve accumulated engineering knowledge, retain actual defect-detection capability, and extend Coverage for new specifications.

IceT, SkyTower, and agent infrastructure are important, but focusing the program around any current tool could displace the real objective.

# Decision

- Make explicit Verification Knowledge and measurable Coverage the PROVE core.
- Evaluate legacy-to-global Test Package equivalence in two independent ways:
  - preservation of engineer Verification Intent;
  - preservation of actual defect-detection capability.
- Treat the definition of the total verification space as a primary unsolved TF problem.
- Defer the definition of specific Coverage axes until PROVE verification experts approve them.
- Treat IceT, SkyTower, languages, models, RAG, and agent frameworks as replaceable enabling tools.
- Require all subprojects and agents to explain their contribution to the core value.

# Consequences

- Test generation success cannot be reported only through code quality or execution success.
- Test counts and code similarity cannot establish package equivalence.
- Existing Test Cases must be mined as verification knowledge, not merely translated.
- Coverage values remain experimental until their verification space and computation are approved.
- Tool redesign is allowed whenever it better supports the core.
- Root Knowledge must prevent subproject goals from drifting toward tool delivery alone.

# Follow-Up

- Verification experts define the process for constructing the verification space.
- The TF defines evidence for Intent preservation and defect-detection preservation.
- Coverage proposals remain hypotheses until an ADR accepts them.
- Subproject charters inherit this decision through their Root Knowledge lock.
