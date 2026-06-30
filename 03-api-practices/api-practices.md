# API Practices

## Pattern

1. Read the contract.
2. Validate all inputs.
3. Convert types explicitly.
4. Fail closed on unexpected shapes.
5. Keep the UI and data layers in sync.

## Example

```ts
function safeMap(items?: Array<{ id?: string }>): string[] {
  if (!items || items.length === 0) {
    return []
  }
  return items
    .filter((item) => !!item?.id)
    .map((item) => item.id as string)
}
```

## Notes

- Treat any external payload as incomplete.
- Avoid hidden assumptions about array length or field stability.
- Keep recovery logic local and narrow.
