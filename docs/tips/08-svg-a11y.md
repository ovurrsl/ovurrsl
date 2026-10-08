# SVG Accessibility

Decide whether an SVG is decorative or meaningful.

```html
<!-- Decorative icon next to visible text: hide it -->
<button>
  <svg aria-hidden="true" focusable="false">…</svg>
  Save
</button>

<!-- Standalone graphic: give it a name -->
<svg role="img" aria-labelledby="chart-title">
  <title id="chart-title">Monthly commits, January to June</title>
  …
</svg>
```

**Why:** screen readers otherwise announce decorative icons as noise, or skip meaningful graphics entirely.
