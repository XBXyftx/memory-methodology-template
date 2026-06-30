# Callback Type Compatibility

## Goal

Make callback signatures explicit and predictable.

## Rule

- Match the declared input and output types exactly.
- Do not rely on structural coincidence when the call site has stronger constraints.
- If a callback can be missing, encode that in the type instead of guessing.

## Template

```ts
type CompletionHandler = (value: string, count: number) => void

function run(handler?: CompletionHandler) {
  if (!handler) {
    return
  }
  handler('ok', 1)
}
```

## Failure Modes

- Missing guard before invocation
- Wrong arity
- Implicit `any`
- Loss of intent through broad types
