# Repository Guidelines

## Repository Purpose

This repository is the canonical Root Knowledge Bundle for PROVE. It defines shared goals, terminology, architecture, metrics, and governance. Subproject implementation details belong in their owning repositories.

Before working, read:

1. `docs/index.md`
2. `docs/principles/core-value.md`
3. `docs/project/vision.md` and `docs/project/scope.md`
4. `docs/glossary/glossary.md`
5. `docs/governance/generated-artifact-governance.md`
6. Relevant principles, interfaces, and decisions
7. `docs/open-questions/open-questions.md`

Do not infer unresolved facts. Record them as open questions. Capture evolving leader discussions in dated sources and derived `draft` concepts. Never overwrite prior sources or promote content to `stable` without explicit authority.

## Non-Negotiable Project Rule

PROVE's core is not a particular test generator, IceT, SkyTower, language, model, or agent framework. Its core is to preserve and expand SSD verification knowledge, generate broader and better tests, and provide measurable Coverage evidence.

Coverage dimensions and the total verification space are intentionally undefined until the TF's verification experts approve them. Agents may propose and evaluate candidates, but must not present a candidate axis, score, or formula as the PROVE standard.

Every proposal must explain how it advances the core. Tools may change when that better serves the goal.

Test Scenario extraction is the first durable verification-asset priority. Governance of every Scenario and later generated artifact is the next priority. Every stage must declare versioned Inputs and Outputs; every durable Output must have an Evidence-based Review Record before official downstream use.

## Knowledge Organization

Documents under `docs/` follow OKF v0.2. Except for reserved `index.md` and `log.md`, every Markdown file needs YAML frontmatter with `type`. Use `status: draft | stable | deprecated`; default to `draft`. Add `sources` and `generated` metadata.

Root contains cross-project knowledge. Local requirements, APIs, runbooks, and implementation ADRs stay in the owning repository. Promote local knowledge through review when it changes common terms, principles, metrics, capabilities, or interfaces.

## Editing Workflow

- Update existing concept pages instead of creating overlapping documents.
- Link related concepts with bundle-relative Markdown links, such as `/principles/ssd-verification.md`.
- Label facts, proposals, targets, and hypotheses clearly.
- For every stage or Workstream, document Inputs, Outputs, Output Review, downstream consumers, and what cannot yet be decided.
- Preserve superseded thinking in dated sources and logs.
- Add unresolved decisions to `docs/open-questions/open-questions.md`.
- Record meaningful structural changes in `docs/log.md`.
- Use `docs/templates/` when starting a subproject knowledge bundle or ADR.

## Validation

Before submitting changes, run:

```bash
git diff --check
rg --files docs
```

Verify links, YAML, dates, and lifecycle states. Never add `stable` or a `human:` verifier without explicit human review.

## Commits and Reviews

Use imperative subjects such as `Define PROVE failure lifecycle`. Keep commits scoped. Reviews should explain the change, evidence, affected subprojects, open questions, and downstream knowledge-version updates.
