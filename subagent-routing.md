# On-Demand Subagent Routing

This is a generic routing matrix for projects that use optional subagents. The lifecycle, evidence labels, and output contract are defined in [agent-workflow.md](agent-workflow.md).

## Default policy

- Subagents are optional read-only tools, not mandatory phases.
- Start the smallest useful set; parallelize independent roles; stop when the question is answered.
- The primary agent owns decisions, edits, verification claims, and authorized external actions.
- Do not start all roles for every bug, every code edit, every framework file, or every delivery step.

## Do not start a subagent when

- The task is a single-file style, copy, resource, label, or parameter change with no state, API, route, or data-flow impact.
- The user provides the exact file, function, minimal change, and acceptance condition, and there is no workspace or history risk.
- The task only fixes a Markdown link, formatting issue, or prompt wording.

## Routing matrix

| Task signal | Smallest role | Add only when needed |
|---|---|---|
| Issue or requirement history is unclear | `memory-router` | Stop after locating the relevant entries |
| Target files have local changes or multiple repositories are involved | `workspace-guardian` | Inspect only the named files and diffs |
| New behavior, interface, state, or reuse is unclear | `chain-mapper` | Add `architecture-reviewer` if multiple modules emerge |
| Bug entry point or call path is unclear | `bug-path-tracer` | Add `log-analyzer` when logs or runtime evidence exist |
| Logs, crash reports, traces, or multi-step reproduction exist | `log-analyzer` | Add `bug-path-tracer` for source correlation |
| Cross-module, global state, routing, shared component, or service behavior | `architecture-reviewer` + `chain-mapper` | Add the bug or requirement-specific role as appropriate |
| Framework code has state, lifecycle, gesture, component API, or compile risk | `domain-compliance-reviewer` | Skip for pure style/resource changes |
| Complex change needs human or device regression | `verification-planner` | Add only when the impact surface is known |
| Completed work needs multiple memory entries or a handoff | `handoff-summarizer` | Skip for a one-line index update |
| Session context or workspace state is missing/abnormal | `preflight-context` | Skip in a normal session after the bootstrap checks |

## Examples

### Pure presentation change

Change a color token, copy string, icon, spacing value, or existing modifier in one file. The primary agent handles it directly and records a short human visual check if needed.

### Reproduction with logs

A runtime bug includes a reproduction sequence and archived logs. Run `log-analyzer`; add `bug-path-tracer` only if the source entry point or state consumer is unclear.

### Cross-module behavior

A requirement changes shared state, routing, a service, or a reusable component. Run `chain-mapper` and `architecture-reviewer`; add `verification-planner` only after the impact surface is understood.

### Simple requirement

A page already has the required flow and only needs a known parameter or label change. The primary agent handles it directly; do not start a history or architecture role without a concrete uncertainty.

## Role contract

Each role should receive:

```text
Task: one-sentence goal
Type: BUG / REQ / review / documentation / analysis
Scope: files, modules, repositories, and evidence paths
Known facts: current clues and protected changes
Question: one concrete question to answer
Output: facts, risks, next action, and stop reason
Constraint: read-only unless explicitly authorized otherwise
```

Role names are labels, not a required implementation. Rename them to match the client or project, but keep the trigger boundaries and output contract.
