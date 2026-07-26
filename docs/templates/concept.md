---
type: Template
title: OKF Concept Template
description: Starter metadata and sections for new PROVE knowledge concepts.
tags: [prove, template, okf]
status: draft
sources:
  - id: okf-spec
    resource: https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md
    title: Open Knowledge Format v0.2
    author: team:google-cloud
    last_modified: 2026-07-24
generated: { by: openai-codex/gpt-5, at: "2026-07-26T00:00:00+09:00" }
---

# Frontmatter Template

```yaml
---
type: "<descriptive concept type>"
title: "<human-readable title>"
description: "<one-sentence description>"
tags: [prove]
status: draft
sources:
  - id: "<stable-source-id>"
    resource: "<bundle path or URL>"
    title: "<source title>"
    author: "<human:id | team:id | process:id | producer/version>"
    last_modified: YYYY-MM-DD
generated: { by: "<actor>", at: "<ISO 8601 datetime>" }
---
```

# Content Guidance

- State the concept and its scope directly.
- Separate facts, accepted decisions, proposals, and hypotheses.
- Link related concepts.
- Add unresolved points to `/open-questions/open-questions.md`.
- Add `verified` only after an actual source check.
- Change `status` to `stable` only after review.
