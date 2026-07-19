# Shared Agent Workflow

> A provider-neutral protocol for a primary AI agent and optional subagents.
> Project rules remain in [rules.md](rules.md); task routing remains in [subagent-routing.md](subagent-routing.md).

## 1. Roles

- The primary agent interprets the request, defines scope, selects subagents, verifies evidence, edits files, and requests authorization.
- Subagents are optional, read-only context tools. They collect targeted evidence, trace flows, review risks, or prepare verification checklists.
- A subagent result is not automatically a project fact. The primary agent must verify important paths, claims, and diffs before using them.
- When multiple AI clients are used, keep one source prompt for each subagent and generate or adapt client-specific files from that source.

## 2. Lifecycle

### A. Classify the request

Record the smallest useful context:

```text
Task type: BUG / REQ / review / documentation / read-only analysis / other
Goal: the result the user wants
Scope: repository, module, page, file, or document entry
Evidence: symptoms, logs, screenshots, test feedback, or source clues
Write scope: read-only or allowed paths; commit authorization if any
Stop condition: the fact or verification result that ends this task
```

If the target file, function, change, and acceptance criteria are already clear, and there is no history uncertainty, workspace risk, or cross-module impact, handle the task directly.

### B. Read progressively

- Read the workspace bootstrap instructions first, then the global memory index and project rules.
- Follow the relevant requirement, bug, API, review, or reference index instead of scanning the whole memory tree.
- Read document-authoring rules only when creating, moving, renaming, splitting, archiving, or materially updating memory documents.
- Load domain skills only when the task needs framework-specific implementation or error guidance.

### C. Orchestrate on demand

1. Select the smallest role set from [subagent-routing.md](subagent-routing.md).
2. Start independent roles in parallel when the client supports it.
3. Stop when the assigned question is answered. Add at most one follow-up batch unless the user requests a deep review.
4. Never start a default bundle merely because code, a framework file, or a delivery step is involved.

### D. Merge evidence

Use explicit labels:

| Label | Meaning |
|---|---|
| `source fact` | Directly shown by current source, configuration, or diff |
| `historical conclusion` | Recorded in memory or an older plan; verify against current source |
| `user/test feedback` | Supplied by a user, tester, device run, or external system |
| `inference` | An explanation derived from evidence, not yet proven |
| `unconfirmed` | Missing source, log, test data, or user confirmation |
| `verified` | Supported by an explicit verification result |

Do not turn a subagent suggestion into a loaded skill, static analysis into a build/device result, or a commit identifier into test evidence.

### E. Execute and close

- Form a minimal change plan before editing.
- Recheck the diff, temporary diagnostics, links, indexes, and protected workspace changes after editing.
- Record actual checks and separate AI checks from human/device verification.
- Update the relevant entry and parent indexes when documentation changes.
- Do not commit, push, submit, restore, or delete files without the required authorization.

## 3. Common output contract

Every subagent should use this order and omit irrelevant detail:

```text
Applicability: applicable / not applicable; matched trigger
Scope checked: what was checked and excluded
Source facts: paths, functions, fields, relationships, evidence locations
Historical conclusions: valid, obsolete, or conflicting records
Risks and unconfirmed items: missing evidence and possible impact
Next action: the smallest action for the primary agent
Stop reason: sufficient evidence / not applicable / external evidence missing / scope limit
```

Subagents should not provide generic whole-repository advice, paste large source or vendor documents, or continue searching after the assigned question is answered.

## 4. Minimum inputs and stop conditions

| Task | Minimum input | Stop condition |
|---|---|---|
| Style/resource change | target file and expected visual change | no state, API, or data-flow impact; usually no subagent |
| Small requirement | requirement entry, target file, acceptance description | existing chain and minimal change are clear |
| Unclear history | issue ID or keywords | return the most relevant entries and stop |
| Log-based bug | reproduction, log path, timeline, or tag | key assumptions are confirmed/excluded, or evidence is missing |
| Unclear code path | entry point, symptom, page, or field | path to state/UI/service and breakpoints are clear |
| Cross-module design | desired behavior, related modules, similar flow | reuse chain, impact surface, and risks are clear |
| Domain compliance review | file/diff, intent, known concerns | relevant syntax, state, lifecycle, and API risks are covered |
| Complex verification | changed files, impact surface, test data | main, reverse, edge, and human-only checks are listed |
| Documentation archive | entry, sources, allowed scope | entry, child evidence, parent indexes, and links are consistent |

## 5. Memory writing workflow

When the task changes the memory tree:

1. Choose the level: root index, section README, item entry, or evidence child document.
2. Identify the source of each claim; separate facts, historical records, inferences, and unconfirmed items.
3. Keep the entry short: status, conclusion, implementation summary, verification state, and links.
4. Move logs, screenshots, failed plans, full traces, and long reviews into the matching child directory.
5. Update parent indexes after adding, moving, renaming, or changing the status of an item.
6. Review real links, duplicate entries, contradictory statuses, sensitive content, length, and factual wording.

Recommended status terms include `implemented`, `static review complete`, `verified`, `pending human verification`, `pending test data`, and `unable to verify: <reason>`.

## 6. Multi-client synchronization

- Edit the source prompt files only; do not hand-edit generated client artifacts.
- Use a temporary source tree when a migration tool might also process workspace instructions.
- Dry-run first, write second, validate the generated target, and inspect the report.
- Preserve unrelated client configuration and never let an agent migration overwrite the workspace bootstrap file.
