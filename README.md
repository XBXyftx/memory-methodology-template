# Long-Term Memory Methodology Template

A portable, progressive-indexing documentation scaffold for capturing project knowledge, rules, requirements, bug investigations, and operational lessons in a maintainable format.

## What This Is

This template provides a directory structure and document conventions for building a project long-term memory that an AI assistant can navigate efficiently. It is not tied to any specific language, framework, or product.

## Key Ideas

- **Progressive indexing** — root index → section README → item entry → child evidence files. Each level stays short; detail flows downward.
- **One canonical entry per item** — requirements and bugs each have a single entry point with a matching subdirectory for evidence.
- **Stable rules vs. live state** — durable methodology and writing rules are kept separate from ephemeral handoff notes.
- **Evidence-driven** — conclusions are backed by investigation notes, not inferred from commit labels.

## Directory Map

| Dir | Purpose |
| --- | ------- |
| `00-index/` | Navigation anchor, points to the root index |
| `01-onboarding/` | Concise session bootstrap and constraints |
| `02-requirements/` | Requirements, analysis, design, implementation records |
| `03-api-practices/` | API patterns, type contracts, technical constraints |
| `04-operations/` | Operational history and archival notes |
| `05-reference/` | Project overview, architecture hotspots, skill guides, external references, lessons |
| `06-code-review-fixes/` | Review findings and repair summaries |
| `07-bug-reports/` | Bug investigations, fix plans, verification archives |

## Root Files

| File | Purpose |
| ---- | ------- |
| `MEMORY.md` | Global navigation index and core principles |
| `rules.md` | Mandatory rules for feature work, bug repair, and documentation |
| `document-authoring-rules.md` | Naming, indexing, link, archive, and review policies for the memory tree |
| `AI-handover.md` | Current-status snapshot for session handoff |

## How to Use

1. Copy the scaffold into your project workspace.
2. Replace every `<placeholder>` with concrete, non-sensitive content.
3. Follow the rules in `document-authoring-rules.md` when creating or splitting documents.
4. Keep the root index and section READMEs up to date.
5. Do not store secrets, private paths, or proprietary source details here.

## License

This template is provided as a starting point. Adapt it to your own workflow and constraints.
