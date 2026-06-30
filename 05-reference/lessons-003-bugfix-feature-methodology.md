# Bugfix and Feature Methodology

## Bug Repair Flow

1. Record the issue.
2. Reproduce or capture evidence.
3. Split the problem into data, state, routing, and UI layers.
4. Isolate the root cause.
5. Design the smallest valid fix.
6. Implement the change.
7. Verify with factual status only.
8. Archive the result.

## Feature Development Flow

1. Index the request.
2. Preserve the original requirement.
3. Identify the nearest existing flow.
4. Define the minimum difference.
5. Design data, state, UI, error handling, and verification.
6. Implement the smallest useful version.
7. Record what remains out of scope.

## Review Checklist

- Evidence is sufficient.
- Change scope is minimal.
- External data is validated.
- Side effects are controlled.
- Verification is explicit.
- Temporary traces are removed.

## Resume-Friendly Summary

- Used evidence-driven debugging.
- Reused existing architecture where possible.
- Kept the change surface minimal.
- Verified with clear status language.
