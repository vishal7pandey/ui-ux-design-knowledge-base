# Gradients and Visual Effects

Gradients and visual effects can add depth, hierarchy, and brand expression. When overused, they become noise. The key is restraint and purpose.

---

## 1. Gradients

### When to use gradients

- To create depth or surface variation.
- To draw attention to a hero or CTA.
- To express brand identity.
- To imply light and shadow subtly.

### When to avoid

- Behind body text (reduces readability).
- On every button and card (dilutes impact).
- As a default for backgrounds.
- When they reduce accessibility.

### Gradient types

| Type | Use case |
|------|----------|
| **Linear** | Subtle backgrounds, buttons, cards. |
| **Radial** | Spotlight, focus, orbs. |
| **Angular / conic** | Progress, rare emphasis. |
| **Mesh** | Brand expression, hero sections. |

### Best practices

- Use 2–3 colors max.
- Ensure text on gradients passes WCAG contrast.
- Keep gradients subtle; avoid neon transitions.
- Use color stops that match the brand palette.
- Test in dark mode and on different screens.
- Avoid overly long color transitions that feel dated.

---

## 2. Shadows

### When to use shadows

- To show elevation and layering.
- To lift interactive elements like buttons and cards.
- To create focus and depth.

### Best practices

- Use a consistent shadow scale (e.g., small, medium, large).
- Shadows should be soft, not harsh.
- Use color and opacity to match the background.
- Darker backgrounds need darker, less opaque shadows.
- Do not use shadows to make everything feel elevated.

---

## 3. Blur and Backdrop Effects

### Backdrop blur

- Used for modals, sheets, and floating panels.
- Keeps the background visible but out of focus.
- Use sparingly; too much blur reduces performance.

### Glassmorphism

- Frosted glass effect with blur, transparency, and subtle border.
- Trendy but can reduce readability.
- Ensure content on glass still passes contrast.

---

## 4. Glows and Halos

- Use for focus states, active states, and brand accents.
- Keep glows subtle and consistent with the color system.
- Avoid glows on every focusable element.

---

## 5. Texture and Pattern

- Use subtle textures to add warmth.
- Avoid busy patterns behind text.
- Use brand patterns sparingly.

---

## 6. Accessibility

- Effects should not reduce readability or contrast.
- Honor `prefers-reduced-motion`.
- Avoid flashing, pulsing, or rapid effects.
- Do not rely on visual effects to convey meaning.

---

## 7. Performance

- Heavy gradients, blurs, and shadows can slow rendering.
- Prefer CSS over images for gradients.
- Use `will-change` carefully for animated effects.
- Test on lower-end devices.

---

## 8. Common Mistakes

- Gradients on every surface.
- Text over high-contrast gradients.
- Inconsistent shadow scales.
- Overuse of blur and glass effects.
- Effects that slow performance.
- Visual effects that distract from content.
- Not testing in dark mode.

---

## 9. Checklist

- [ ] Gradients serve a purpose and are not overused.
- [ ] Text on gradients passes contrast checks.
- [ ] Gradients are consistent with the brand palette.
- [ ] Shadows follow a clear, consistent scale.
- [ ] Elevation matches the design system.
- [ ] Blur and glass effects do not reduce readability.
- [ ] Glows and halos are used for meaningful states.
- [ ] Effects are tested in dark mode and on low-end devices.
- [ ] `prefers-reduced-motion` is respected.
- [ ] Effects do not hurt performance.
