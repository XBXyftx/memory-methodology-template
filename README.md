# Long-Term Memory Methodology Template

A portable, progressive-indexing documentation scaffold for capturing project knowledge, rules, requirements, bug investigations, and operational lessons in a maintainable format.

> [中文版本](README_zh.md)

## What This Is

This template provides a directory structure and document conventions for building a project long-term memory that an AI assistant can navigate efficiently. It is not tied to any specific language, framework, or product.

## Key Ideas

- **Progressive indexing** — root index → section README → item entry → child evidence files. Each level stays short; detail flows downward.
- **One canonical entry per item** — requirements and bugs each have a single entry point with a matching subdirectory for evidence.
- **Stable rules vs. live state** — durable methodology and writing rules are kept separate from ephemeral handoff notes.
- **Evidence-driven** — conclusions are backed by investigation notes, not inferred from commit labels.
- **On-demand agents** — optional subagents answer focused questions; simple tasks stay on the primary agent.
- **Shared agent contract** — lifecycle, evidence labels, output format, stop conditions, and multi-client synchronization are defined once.

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
| `agent-workflow.md` | Shared primary-agent/subagent lifecycle and output contract |
| `subagent-routing.md` | Generic on-demand subagent routing matrix and examples |

## How to Use

1. Copy the scaffold into your project workspace.
2. Replace every `<placeholder>` with concrete, non-sensitive content.
3. Use `agent-workflow.md` when coordinating subagents or writing memory documents.
4. Use `subagent-routing.md` to select the smallest useful subagent set.
5. Read `document-authoring-rules.md` when creating, moving, splitting, archiving, or materially updating memory documents.
6. Keep the root index and section READMEs up to date.
7. Do not store secrets, private paths, or proprietary source details here.

## License

This template is provided as a starting point. Adapt it to your own workflow and constraints.
