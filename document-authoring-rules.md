# Document Authoring Rules

> This file defines the writing and indexing policy for the portable-long-term-memory tree.
> It is separate from `rules.md`, which covers broader work behavior.

## Scope

These rules apply to every markdown document under `portable-long-term-memory/`.

## Naming Policy

- Use neutral, project-agnostic names unless a document is intentionally a case study.
- Prefer numbered prefixes for indexable series.
- Keep one canonical name per item type.

## Entry Policy

- Each topic must have one clear entry point.
- If a topic grows, add child documents instead of extending the entry indefinitely.
- The entry document should summarize and link downward.

## Link Policy

- Every markdown link in an index must point to an existing file or folder.
- Placeholder links must be marked as future items, not presented as live links.
- Update parent indexes when files are moved or renamed.

## Archive Policy

- Preserve factual content only.
- Do not copy sensitive source details, local paths, or real identifiers.
- If a real example is converted into a template, replace the identifying parts with placeholders or neutral terms.

## Growth Policy

- Keep root indexes short.
- Promote durable generalizations into reference or methodology files.
- Keep one-off cases in requirement or bug folders.

## Review Policy

- Before finishing a documentation pass, check for broken links, duplicate entries, and stale placeholders.
- Use factual status words only.
- For this tree, `REQ-*` and `BUG-*` entries use a single canonical entry file plus a same-ID child folder when needed.
