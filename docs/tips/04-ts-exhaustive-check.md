# Exhaustive Checks

Make the compiler tell you when a union gains a case you forgot to handle.

```ts
type Shape = { kind: 'circle'; r: number } | { kind: 'square'; size: number }

function assertNever(x: never): never {
  throw new Error(`Unhandled case: ${JSON.stringify(x)}`)
}

function area(shape: Shape): number {
  switch (shape.kind) {
    case 'circle':
      return Math.PI * shape.r ** 2
    case 'square':
      return shape.size ** 2
    default:
      return assertNever(shape)
  }
}
```

**Why:** add `{ kind: 'triangle' }` to `Shape` and `area` stops compiling until you handle it, instead of failing at runtime.
