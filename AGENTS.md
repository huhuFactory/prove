# Repository Guidelines

## Repository Purpose

This repository is the canonical Root Knowledge Bundle for PROVE. It defines shared goals, terminology, principles, cross-project architecture, metrics, and governance. IceT, SkyTower, scenario extraction, test generation, and failure analysis implementation details belong in their own repositories.

Before working, read:

1. `docs/index.md`
2. `docs/project/vision.md` and `docs/project/scope.md`
3. `docs/glossary/glossary.md`
4. Relevant principles, interfaces, and decisions
5. `docs/open-questions/open-questions.md`

Do not infer unresolved facts. Record them as open questions.

## Knowledge Organization

Documents under `docs/` follow OKF v0.2. Every Markdown file except reserved `index.md` and `log.md` files must have YAML frontmatter with at least `type`. Use `status: draft | stable | deprecated`; new knowledge defaults to `draft`. Add `sources` for derived claims and `generated` for material edits.

Root knowledge contains only information shared across multiple projects. Project-local requirements, APIs, runbooks, and implementation ADRs stay in the owning repository. Promote local knowledge to Root through review when it changes common terminology, principles, capabilities, metrics, or interfaces.

## Editing Workflow

- Update existing concept pages instead of creating overlapping documents.
- Link related concepts with bundle-relative Markdown links, such as `/principles/ssd-verification.md`.
- Preserve confirmed facts and clearly label proposals, targets, and hypotheses.
- Add unresolved decisions to `docs/open-questions/open-questions.md`.
- Record meaningful structural changes in `docs/log.md`.
- Use `docs/templates/` when starting a subproject knowledge bundle or ADR.

## Validation

No build system is configured. Before submitting changes, run:

```bash
git diff --check
rg --files docs
```

Verify internal links, YAML syntax, dates, and lifecycle states. Do not mark a document `stable` or add a `human:` verifier without explicit human review.

## Commits and Reviews

Use concise imperative subjects, for example `Define PROVE failure lifecycle`. Keep commits scoped to one knowledge change. Pull requests should explain the changed decision or concept, affected subprojects, evidence, unresolved questions, and required downstream knowledge-version updates.
