# Responsive Typography

`clamp(min, preferred, max)` scales a value fluidly between two limits.

```css
h1 {
  font-size: clamp(1.75rem, 1rem + 3vw, 3rem);
}
```

**Why:** one line replaces a stack of media queries. Mixing `rem` into the preferred value keeps text zoomable for users who change their browser font size.
