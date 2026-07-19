# Portable Long-Term Memory Index

> Last updated: 2026-07-19
> Purpose: keep only the global navigation, current state placeholders, and the most important reusable conclusions. Details belong in the subdirectory README files and topic documents.

## Must Read

- **[Project Rules](rules.md)** - Read before any development, bug fixing, documentation archiving, or process updates.
- **[Document Authoring Rules](document-authoring-rules.md)** - Naming, indexing, link, and archive policy for this portable tree.
- **[AI Handover](AI-handover.md)** - Current status, open work, and handoff cues.
- **[Project Overview](05-reference/project-overview.md)** - Abstract project facts, main entry points, and architectural notes.
- **[Current Architecture Hotspots](05-reference/analysis-002-current-architecture-hotspots.md)** - Risk-prone flows and repeated investigation targets.
- **[Bugfix and Feature Methodology](05-reference/lessons-003-bugfix-feature-methodology.md)** - Evidence chain, root-cause isolation, minimal change, verification, and write-up format.
- **[Skill Lookup Guide](05-reference/analysis-003-harmony-skills-lookup-guide.md)** - When a task needs framework or tool-specific guidance.
- **[Shared Agent Workflow](agent-workflow.md)** - Shared lifecycle, evidence labels, output contract, stop conditions, and memory-writing workflow.
- **[On-Demand Subagent Routing](subagent-routing.md)** - Generic task matrix and examples for selecting the smallest useful subagent set.

## Read by Task

- New session handoff: [01-onboarding/onboarding-prompt.md](01-onboarding/onboarding-prompt.md)
- Requirements work: start at [02-requirements/README.md](02-requirements/README.md)
- Bug repair: start at [07-bug-reports/README.md](07-bug-reports/README.md)
- API, callbacks, null-safety: [03-api-practices/README.md](03-api-practices/README.md)
- Reference and lessons: [05-reference/README.md](05-reference/README.md)
- Agent orchestration: [agent-workflow.md](agent-workflow.md) -> [subagent-routing.md](subagent-routing.md)

## Directory Map

- [00-index](00-index/README.md) - top-level navigation anchor
- [01-onboarding](01-onboarding/README.md) - short session bootstrap context
- [02-requirements](02-requirements/README.md) - requirements, analysis, implementation, and version indexes
- [03-api-practices](03-api-practices/README.md) - API usage patterns and technical constraints
- [04-operations](04-operations/README.md) - operation history and archival notes
- [05-reference](05-reference/README.md) - project overview, analysis, lessons, and external references
- [06-code-review-fixes](06-code-review-fixes/README.md) - review-driven fixes and their summaries
- [07-bug-reports](07-bug-reports/README.md) - bug investigations, fix plans, and final archives

## Current State Template

- Main project: `<project-name>`
- Current version: `<version-name>` / `<version-code>`
- Main stack: `<framework>` / `<language>`
- Workspace note: this template is isolated and intended for portable methodology transfer.
- Sensitive details are intentionally omitted.

## High-Level Method

1. Read the root index and rules first.
2. Find the most relevant version, bug, or reference index.
3. Work from evidence to conclusion.
4. Keep each document short and use progressive indexing.
5. Record verification status with factual wording only.
6. Start subagents only when a concrete uncertainty, evidence type, workspace risk, or impact surface justifies them.

## Core Principles

- Prefer reuse before inventing new abstractions.
- Model new work after the closest existing flow.
- Minimize changes to the smallest effective surface.
- Treat all external data as untrusted.
- Keep logs, temp notes, and debug traces out of final archives.
- Do not store secrets, private paths, or project-specific source details here.
- Keep one source prompt per subagent when multiple AI clients are supported; generate and validate client-specific adapters from it.
