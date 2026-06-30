# Hotspot Analysis

## Focus Areas

- List flows
- Detail flows
- Local caching and refresh behavior
- Cross-page state
- Side effects from watchers or observers
- Telemetry and sensitive input handling
- Any flow that combines navigation, state, and remote data

## Investigation Questions

1. What is the source of truth?
2. What is cached?
3. Which state is shared across views?
4. What side effects can fire on write?
5. What data is user-controlled?
6. What data must stay private?
7. Which path is the smallest correct fix?

## Notes

- Use this file as a map, not as a full report.
- Put deep analysis into topic documents.
