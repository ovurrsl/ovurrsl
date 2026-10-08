# CSS Variables

Use custom properties (`--token-name`) as design tokens instead of repeating raw values.

```css
:root {
  --color-accent: #58a6ff;
  --radius-md: 8px;
  --space-4: 1rem;
}

[data-theme="dark"] {
  --color-accent: #79c0ff;
}

.button {
  background: var(--color-accent);
  border-radius: var(--radius-md);
  padding: var(--space-4);
}
```

**Why:** one change to a token updates every component, and themes become a matter of redefining variables, not rewriting selectors.
