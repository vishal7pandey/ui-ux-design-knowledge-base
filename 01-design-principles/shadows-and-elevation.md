# Shadows and Elevation

Shadows and elevation help users understand what is on top, what is behind, and what is interactive. Used well, they create a sense of space and hierarchy. Used poorly, they create visual noise and confusion.

---

## 1. What Elevation Communicates

Elevation is the perceived distance of an element above the surface. Higher elevation means closer to the user.

- **Low elevation**: resting state, base surfaces.
- **Medium elevation**: cards, inputs, raised content.
- **High elevation**: modals, floating actions, dropdowns, toasts.

---

## 2. Shadow Scale

A shadow scale defines elevation levels with consistent shadow values.

| Level | Elevation | Use case |
|-------|-----------|----------|
| **0** | Flat | Backgrounds, base layer. |
| **1** | Slight | Subtle cards, resting inputs. |
| **2** | Raised | Default cards, buttons. |
| **3** | Floating | Dropdowns, menus, tooltips. |
| **4** | Modal | Dialogs, side sheets, bottom sheets. |

---

## 3. Shadow Anatomy

A natural shadow has:

- **X offset**: horizontal distance.
- **Y offset**: vertical distance (larger values feel higher).
- **Blur radius**: how soft the shadow is.
- **Spread radius**: how much the shadow grows.
- **Color and opacity**: usually a dark color with low opacity.

For most UI, use a small Y offset, moderate blur, and low opacity.

---

## 4. Best Practices

### Keep shadows subtle

- Shadows should be felt, not noticed.
- Avoid pure black; use a dark tint of the background.
- Use low opacity (8%–24%).

### Use shadow for state, not decoration

- Raised on hover or focus.
- Increased elevation for active, dragged, or modal states.
- Consistent with the design system.

### Elevation + Z-index

- Higher visual elevation should match a higher z-index.
- Document how components stack.

### Dark mode shadows

- Dark backgrounds need darker, less opaque shadows.
- In dark mode, use lighter or colored overlays for elevation instead of shadows.
- Example: add a light overlay to a surface rather than a black shadow.

---

## 5. Elevation in Components

| Component | Typical elevation |
|-----------|-------------------|
| **Cards** | 1–2 at rest, 2–3 on hover. |
| **Buttons** | 1–2 at rest, 3–4 on hover, lower on press. |
| **Dropdowns / menus** | 3–4. |
| **Modals** | 4–5. |
| **Floating action buttons** | 3–4, higher on hover. |

---

## 6. Common Mistakes

- Every element has a shadow.
- Inconsistent shadow scale across components.
- Pure black shadows at high opacity.
- No shadow on dropdowns or modals.
- Elevation that does not match the component hierarchy.
- Shadows in dark mode that are too visible or too hard.
- Heavy shadows that reduce performance.

---

## 7. Accessibility

- Do not rely on shadow alone to convey meaning.
- Pair elevation with contrast, borders, or other cues.
- Honor `prefers-reduced-motion` for animated elevation changes.
- Ensure modals and elevated surfaces have clear focus states.

---

## 8. Performance

- Use CSS `box-shadow` over images.
- Avoid animating large, heavy shadows.
- Do not create hundreds of layered shadows.
- Test on lower-end devices and mobile.

---

## 9. Checklist

- [ ] Shadow scale is documented and consistent.
- [ ] Shadows are subtle and purposeful.
- [ ] Elevation matches the component hierarchy.
- [ ] Hover, focus, and active states change elevation consistently.
- [ ] Dark mode shadows are adjusted.
- [ ] Modals and dropdowns have sufficient elevation.
- [ ] Elevation is paired with other visual cues.
- [ ] Performance is tested on low-end devices.
- [ ] `prefers-reduced-motion` is respected for elevation animations.
- [ ] Z-index and elevation are aligned.
