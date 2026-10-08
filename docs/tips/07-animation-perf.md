# Animation Performance

Animate `transform` and `opacity`, not layout properties like `top`, `left` or `width`.

```css
/* ❌ triggers layout on every frame */
.card:hover { top: -4px; }

/* ✅ handled by the compositor */
.card { transition: transform 200ms ease; }
.card:hover { transform: translateY(-4px); }

@media (prefers-reduced-motion: reduce) {
  .card { transition: none; }
}
```

**Why:** the browser can move or fade a layer on the GPU without recalculating layout, which keeps animations at 60 fps. Respecting `prefers-reduced-motion` keeps them accessible.
