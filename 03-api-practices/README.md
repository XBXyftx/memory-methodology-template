# 03-api-practices - API Practices and Constraints

> Store API usage patterns, callback compatibility rules, and technical constraints.

## Purpose

- Stable API usage patterns
- Type compatibility notes
- Data flow and UI flow contracts
- Framework limitations and constraints

## Naming

| Type | Format | Example |
|------|--------|---------|
| Practice case | `api-practices.md` | fixed single file |
| Type rules | `{topic}_callback_types.md` | `feedback_callback_types.md` |
| Constraints | `constraint-{framework}-{topic}.md` | `constraint-arkts-builder.md` |

## Current Files

| File | Description |
|------|-------------|
| [`api-practices.md`](api-practices.md) | Generic API and null-safety practice notes |
| [`feedback_callback_types.md`](feedback_callback_types.md) | Generic callback compatibility example |

## Maintenance

- Add code samples when a rule is technical rather than conceptual.
- Explain why a rule exists.
- Keep sensitive project details out of this directory.
