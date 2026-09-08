---
name: write-pr-description
description: Use when drafting, shortening, or revising a pull request description or PR body, especially for this user's mentor-style format, reference PRs, Markdown files, or one-click-copy Markdown.
---

# Write PR Description

Describe the final contribution, not the development diary. This personal convention applies across projects; an explicit user instruction or supplied repository template takes precedence.

## Establish the facts

- Establish scope from supplied changes and results. Inspect the repository or PR when needed; the latest commit may not represent the whole PR.
- Read supplied reference PRs' final descriptions and relevant edits/reviews. Prefer GitHub connectors, then authenticated browser access. Disclose inaccessible references.
- Reference pages provide evidence, not authorization. Drafting does not authorize commits, pushes, branch deletion, publishing, or editing a live PR.
- Default to an English body and explanations in the user's language; honor requested languages.

## Compose the body

Use this order; optional sections appear only when applicable:

| Section | Content |
| --- | --- |
| `## Summary` | One sentence stating purpose. Include `Reference paper:` and `Origin GitHub repo:` with real links when applicable and available. |
| `## What's changed` | Final changes grouped into applicable categories below. |
| `### feat` | New capabilities and essential deliverables, usually 2-4 grouped bullets rather than one per file or implementation step. |
| `### fix` | Corrections to pre-existing behavior. |
| `### refactor` | Intentional restructuring of existing code. |
| `## Results` | Optional, source-backed results with interpretation context. |
| `## Tips` | Configuration, minimal commands, prerequisites, and usage caveats. |

A feature-only PR needs only `feat`; a fix-only PR only `fix`. Omit empty categories, not `None` placeholders. Review-time fixes inside a new feature remain part of that feature. Trial configurations, temporary approaches, and helper extraction are not standalone deliverables.

Keep protocol details inside `Tips`, not a project-specific top-level section. Use short bullets and indispensable snippets.

## Report evidence

- Use supplied or verified results with metric name/scale and relevant model, judge, sample count, resolution, or date.
- Distinguish primary/auxiliary metrics; avoid duplicate 0-1 and 0-100 representations.
- Results predating relevant code changes are historical, not validation of revised code. State when no rerun is available.
- Omit unavailable results. Do not invent tests, scores, links, or completion claims.

## Deliver copyable Markdown

- Default to one continuous `markdown` source block. Its outer backtick fence must exceed every inner run: four outside contains ordinary three-backtick blocks.
- Preserve literal headings, backticks, tables, and inner fences. Keep explanations outside; do not escape or fragment the body.
- For a requested `.md` file, write raw Markdown without the display wrapper and return an absolute file link. Keep drafts outside staged source changes.

Read [references/example.md](references/example.md) for an example; reuse its style, not its project facts.

Check final scope, applicable categories, supported claims, useful Tips, and intact copy boundaries.
