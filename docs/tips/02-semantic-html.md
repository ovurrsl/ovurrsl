# Semantic Landmarks

Use landmark elements instead of anonymous `<div>`s.

```html
<header>…</header>
<nav aria-label="Main">…</nav>
<main>
  <article>…</article>
  <aside>…</aside>
</main>
<footer>…</footer>
```

**Why:** screen-reader users can jump straight between landmarks, and the markup documents the page structure for the next developer.
