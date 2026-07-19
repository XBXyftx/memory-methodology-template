# Project Rules

> Applies to all feature work, bug repair, code review fixes, investigations, and documentation archiving.
> Priority order: explicit user instruction > these rules > local skill guidance > default coding habits.

## Rule Index

| # | Rule | Core Idea |
|---|------|-----------|
| 1 | Task boundary and code facts | Know what may be edited, and trust the current source of truth |
| 2 | No empty early return | Use explicit branching and visible termination paths |
| 3 | Reuse first | Prefer existing utilities, components, and interfaces |
| 4 | Mirror nearby flows | Model new logic after the closest existing chain |
| 5 | Minimal change | Change the smallest surface that solves the problem |
| 6 | Git / SVN boundaries | Only commit or submit when authorized |
| 7 | Short docs and progressive indexing | Keep entry docs small and push details downward |
| 8 | Zero-trust external data | Validate every boundary input |
| 9 | Evidence first | Ask for help when reliable evidence is missing |
| 10 | Bug workflow | Record, isolate, design, implement, verify, archive |
| 11 | Feature workflow | Index first, then implement |
| 12 | State and side effects | Use stable semantics and control watchers carefully |
| 13 | Telemetry and sensitive data | Align metrics first and avoid leaking user content |
| 14 | Verification and regression | Verify with facts and cover key paths |
| 15 | No toolchain execution | AI does not run build/install/packaging flows when prohibited |
| 16 | Clean logs before submission | Remove temporary diagnostics before handoff |
| 17 | Consult skills when needed | Load the right domain guidance before editing |
| 18 | Pre/post checklist | Self-check before and after changes |
| 19 | On-demand subagents and shared protocol | Choose the smallest role set and use one evidence/output contract |

---

## 1. Task Boundary and Code Facts

- Read-only requests stay read-only.
- Documentation-only work should only touch the memory tree.
- If documentation and source disagree, record the conflict and stop for confirmation.
- Do not overwrite or normalize unrelated work.

## 2. No Empty Early Return

```ts
if (condition) {
  return
}
```

Prefer:

```ts
if (!condition) {
  // continue the real work
}
```

## 3. Reuse First

1. Look for existing helpers, state fields, components, and interfaces.
2. Compare with the nearest similar flow.
3. Extend before inventing.
4. Add new code only for the irreducible difference.

## 4. Mirror Nearby Flows

Ask:

1. What is the closest existing case?
2. What is its data source?
3. Where is its model defined?
4. How does state move through the flow?
5. How does the UI consume it?
6. What is genuinely different here?
7. Can the difference be isolated?
8. Can the fix stay small?

## 5. Minimal Change

- No unrelated refactors.
- No future-proofing by default.
- No extra abstraction without clear value.
- State what changes and what stays untouched.

## 6. Git / SVN Boundaries

- Only create commits or submissions when the user asks.
- Never touch unrelated diffs.
- Record hash or revision only after the action actually happened.

## 7. Short Docs and Progressive Indexing

- One entry document should stay small.
- Move logs, images, traces, and long analysis into child folders.
- Keep the root index navigable.

## 8. Zero-Trust External Data

- Validate nulls, arrays, types, ranges, URLs, and identifiers.
- Check both at the utility level and at the call site.
- Renderers and handlers still need their own guards.
- Do not let one malformed item corrupt the full flow.

## 9. Evidence First

- If you cannot verify it from source, logs, or a reliable tool, ask for help.
- Describe what is missing and why it matters.

## 10. Bug Workflow

1. Record the issue.
2. Capture evidence.
3. Isolate the root cause.
4. Design the smallest valid fix.
5. Implement.
6. Verify.
7. Archive.

## 11. Feature Workflow

1. Index the requirement.
2. Preserve the source description.
3. Split the work into data, state, UI, error handling, and verification.
4. Reuse existing flows where possible.
5. Keep the first version small.

## 12. State and Side Effects

- Use stable business semantics, not visual progress values, for business decisions.
- Isolate caches by scope.
- Audit watchers before adding state writes.

## 13. Telemetry and Sensitive Data

- Define event name, trigger timing, deduping, and non-trigger cases first.
- Never log sensitive user content.
- Use stable keys for metric parameters.

## 14. Verification and Regression

- Cover primary, reverse, and edge paths.
- Record what was verified and what remains unverified.
- Do not claim success without evidence.

## 15. No Toolchain Execution

- When this policy is active, AI does not run build, install, packaging, or signing tools.
- Keep verification language factual and limited.

## 16. Clean Logs Before Submission

- Remove temporary diagnostics, debug prints, and one-off markers.
- Keep only logs that have a clear business reason.

## 17. Consult Skills When Needed

- Load the relevant skill before touching framework-specific code or error analysis.
- Record which skill and why it was used in the related document.

## 18. Pre / Post Checklist

- Confirm the task type.
- Confirm the allowed edit scope.
- Check for related existing solutions.
- Check boundary input validation.
- Confirm the required verification method.
- Clean temporary traces before archiving.

## 19. On-Demand Subagents and Shared Protocol

- Subagents are optional read-only context tools, not mandatory steps for every task.
- Simple, explicit, single-file work should remain on the primary agent.
- Select roles from [subagent-routing.md](subagent-routing.md); use [agent-workflow.md](agent-workflow.md) for lifecycle, evidence labels, output, and stop conditions.
- Start independent roles in parallel when possible, stop when the question is answered, and add at most one follow-up batch unless deep review is requested.
- The primary agent verifies important subagent claims before editing or recording them as facts.
- Subagent prompts should receive a concrete question, scope, evidence, protected changes, and stop condition.
- When multiple clients are supported, edit one prompt source and regenerate client-specific artifacts; do not maintain competing prompt bodies by hand.
- A migration must not overwrite workspace bootstrap instructions or unrelated client configuration.
