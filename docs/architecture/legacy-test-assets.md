---
type: Architecture
title: Legacy Test Package and Hardware Structure
description: Current understanding of IceT, heterogeneous hardware, package-local libraries, and legacy evidence gaps.
tags: [prove, icet, legacy, test-library, hardware]
status: draft
sources:
  - id: discovery-2026-08-02
    resource: /sources/discovery-2026-08-02.md
    title: PROVE working discovery discussion
    author: human:prove-leader
    last_modified: 2026-08-02
  - id: legacy-scenario-analysis-directive-2026-08-02
    resource: /sources/legacy-scenario-analysis-directive-2026-08-02.md
    title: PROVE leader Legacy Scenario analysis directive
    author: human:prove-leader
    last_modified: 2026-08-02
generated: { by: openai-codex/gpt-5, at: "2026-08-02T00:00:00+09:00" }
---

# Execution Structure

IceT abstracts several validation hardware types rather than one common physical platform. Known examples include multiple PCIe generations and separate Client SSD validation hardware.

```text
Multiple validation hardware types
→ IceT abstraction
→ command- and operation-level API
→ team-specific Test Libraries
→ JavaScript Test files
```

The exact hardware inventory and applicability rules are not yet documented.

# Package Structure

Each verification team manages a Git repository containing both its JavaScript Test files and team-specific Test Libraries. The libraries compose IceT primitives into repeated or higher-level verification behavior.

Test files and libraries are one inseparable version unit. Scenario extraction must analyze a complete repository revision, but it resolves only the imports and call paths needed to understand the relevant verification behavior.

# Knowledge Location

Engineering knowledge may exist in:

- Individual Test flow and assertions
- Team-library composition, retry, recovery, and common behavior
- Partial comments or descriptions
- Inconsistent Specification references
- Historical execution, Failure analysis, and Bug information

# Evidence Gap

There is no reliable identifier linking a Test to its execution history, Failure analysis, or Bug record. Any reconstructed relationship must preserve evidence and distinguish confirmed, probable, candidate, and unlinked states. Exact state names are not approved.

# Analysis Implication

The analysis unit is not one JavaScript file in isolation because verification meaning may be implemented in Package Libraries. Nevertheless, building a complete Package-wide Call Graph is not a PROVE outcome.

Use Scenario-centered semantic slicing:

```text
Legacy Test
→ follow only relevant Library behavior
→ recover Intent, stimulus, state effects, Oracle, recovery, and applicability
→ validate against execution evidence where available
→ produce Scenario and reusable Verification Knowledge
```

Code relationships are provenance and confidence Evidence. Scenario and Verification Knowledge are the primary outputs.

# State Dependency Status

Legacy Test-to-Test State dependencies are not declared or managed, so their existence is unknown rather than disproven. Analysis may identify candidate state effects or hidden dependencies, but must label them as hypotheses until execution Evidence validates them. Confirmed findings should become explicit PROVE State Contracts rather than preserved hidden order rules.
