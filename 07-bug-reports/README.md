# Bug Workflow and Index

> Store bug reports, investigation notes, fix plans, and final archives.

## Directory Structure

```text
07-bug-reports/
├── BUG-XXXX.md
├── BUG-XXXX/
└── README.md
```

## Workflow

1. Main bug document is the entry point.
2. Logs, screenshots, deep investigations, and plan reviews go into the matching subdirectory.
3. The main document keeps only the summary, root cause, fix summary, verification state, and child document index.
4. Keep each document short and split long notes into child files.

## Statuses

| Status | Meaning |
| ------ | ------- |
| To triage | Recorded, not yet analyzed |
| Investigating | Root cause analysis in progress |
| Ready to implement | Solution selected, coding pending |
| Fixed, pending verification | Code changed, verification pending |
| Verified | Confirmed by testing or approved evidence |
| Rolled back | Wrong fix removed, redesign needed |

## Index

| Bug ID | Title | Status |
| ------ | ----- | ------ |
| [BUG-0001](BUG-0001.md) | Placeholder bug one | To triage |
| [BUG-0002](BUG-0002.md) | Placeholder bug two | Investigating |

## Maintenance

- Keep statuses factual.
- Do not infer verification from a commit-like label.
- Keep sensitive details out of the index.
