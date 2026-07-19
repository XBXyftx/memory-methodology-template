# Onboarding Prompt

Use this prompt when a new session needs a concise handoff.

## Snapshot

- Project: `<project-name>`
- Language: `<language>`
- Stack: `<framework>`
- Version: `<version-name>` / `<version-code>`
- Memory root: `portable-long-term-memory/`

## Required Reading

1. Read the root [MEMORY.md](../MEMORY.md).
2. Read [rules.md](../rules.md).
3. Read [agent-workflow.md](../agent-workflow.md) and [subagent-routing.md](../subagent-routing.md) only when subagents or workflow maintenance are in scope.
4. Read [document-authoring-rules.md](../document-authoring-rules.md) only when memory documents will be created, moved, split, archived, or materially updated.
5. Read the relevant requirements or bug index.
6. Read the closest reference notes before proposing changes.

## Working Rules

- Keep changes minimal.
- Reuse existing flows before inventing new ones.
- Treat external data as untrusted.
- Record evidence before conclusions.
- Do not start a default subagent bundle; choose the smallest role set justified by the task.
- Do not store real secrets, private paths, or proprietary source details here.

## Risk Areas

- State drift
- Weak validation
- Overscoped edits
- Missing verification
- Unclear ownership of cross-cutting behavior

## Output Style

When writing a handoff, include:

- current status
- open questions
- evidence gathered
- next action
- verification state
