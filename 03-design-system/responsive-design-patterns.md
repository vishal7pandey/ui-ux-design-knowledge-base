# Responsive Design Patterns

Responsive design means building interfaces that adapt gracefully to any screen size, resolution, or input method. Modern responsive design combines fluid layouts, media queries, container queries, and user-preference adaptation.

---

## 1. Core Principles

- **Mobile-first**: start with the smallest screen, then add complexity as space allows.
- **Content-first breakpoints**: add breakpoints where the layout breaks, not at arbitrary device widths.
- **Fluid over fixed**: prefer relative units (`%`, `rem`, `em`, `fr`) over fixed pixel widths.
- **Component-level responsiveness**: use container queries so components adapt to their own container, not just the viewport.

---

## 2. Breakpoint Strategy

### Recommended set

| Token | min-width | Typical target |
|-------|-----------|----------------|
| `sm` | 640px | Large phones, small tablets |
| `md` | 768px | Tablets (portrait) |
| `lg` | 1024px | Small laptops, tablets (landscape) |
| `xl` | 1280px | Desktops |
| `2xl` | 1536px | Large and wide monitors |

> These values mirror Tailwind CSS and Bootstrap, making them predictable for most teams.

### Content-first approach

1. Build the narrowest layout first.
2. Gradually widen the viewport.
3. When the layout breaks (line length too long, columns too narrow), add a breakpoint.
4. Only override what must change; do not duplicate unrelated rules.

---

## 3. Modern Layout Tools

### CSS Grid with `auto-fit` and `minmax()`

```css
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1rem;
}
```

This produces a responsive card grid without media queries.

### Flexbox with `flex-wrap`

```css
.toolbar {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}
```

Items wrap naturally when there is not enough space.

### Container queries

Container queries respond to the size of a component’s container, not the viewport. They are now supported in 93%+ of browsers.

```css
.card {
  container-type: inline-size;
}

@container (min-width: 400px) {
  .card-inner {
    display: grid;
    grid-template-columns: 120px 1fr;
  }
}
```

**When to use**:

- Reusable components that appear in sidebars, main content, and dialogs.
- Dashboard widgets with the same markup in different contexts.
- Cards that need horizontal and vertical variants.

---

## 4. Fluid Typography

Use `clamp()` to scale type smoothly between a minimum, preferred, and maximum size.

```css
h1 {
  font-size: clamp(1.75rem, 4vw + 1rem, 3rem);
}
```

This avoids jarring size jumps at breakpoints while keeping text readable at all sizes.

### Guidelines

- Set a minimum that is still readable on the smallest screens.
- Use `vw` for the preferred value so it scales with the viewport.
- Set a maximum so it does not become oversized on ultra-wide screens.

---

## 5. Fluid Spacing

Use `clamp()` or CSS variables for spacing that scales with the viewport.

```css
:root {
  --section-padding: clamp(1rem, 5vw, 4rem);
}

section {
  padding: var(--section-padding);
}
```

---

## 6. Images and Media

### Fluid images

```css
img {
  max-width: 100%;
  height: auto;
}
```

### Responsive images

Use `srcset` and `sizes` to serve the right image size:

```html
<img
  srcset="hero-400.jpg 400w, hero-800.jpg 800w, hero-1200.jpg 1200w"
  sizes="(max-width: 600px) 100vw, 50vw"
  src="hero-800.jpg"
  alt="..."
/>
```

### Lazy loading

```html
<img src="photo.jpg" loading="lazy" alt="..." />
```

Apply to images below the fold. Avoid lazy loading above-the-fold images.

---

## 7. Touch and Input Considerations

- **Minimum touch target**: 44×44dp on iOS, 48×48dp on Material Design.
- **Hover support**: use `@media (hover: hover)` to show hover-only affordances.
- **Pointer precision**: increase hit areas and spacing for touch.
- **Keyboard**: ensure all interactive elements are keyboard accessible on all screen sizes.

---

## 8. Common Responsive Patterns

### Off-canvas navigation

A sidebar hidden by default on mobile, toggled with a hamburger or close button.

### Stacked-to-horizontal

Single-column on mobile, multi-column on larger screens.

### Reorder content

Use CSS Grid `order` or source order to place the most important content first on small screens.

### Hide and reveal

Progressively disclose secondary content on small screens; expand on larger screens.

---

## 9. Best Practices

1. Design mobile first; add complexity upward.
2. Use `min-width` media queries, not `max-width`.
3. Prefer container queries for components.
4. Avoid fixed widths; use `max-width` for readable line lengths.
5. Keep text line lengths between 45–75 characters.
6. Test on real devices, not just browser resizing.
7. Respect `prefers-reduced-motion` and `prefers-color-scheme`.

---

## 10. Checklist

- [ ] Base styles cover the smallest viewport.
- [ ] Breakpoints are content-driven, not device-specific.
- [ ] Container queries used for reusable components.
- [ ] Fluid type and spacing avoid breakpoint jumps.
- [ ] Images are responsive and optimized.
- [ ] Touch targets meet minimum size requirements.
- [ ] Keyboard navigation works on all breakpoints.
- [ ] Reduced motion and dark mode preferences are respected.
