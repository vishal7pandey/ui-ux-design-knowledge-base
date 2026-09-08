# Dark Mode and Theming

Theming lets products adapt to user preferences, brand identity, and context. Dark mode is the most common theme, but a strong theming strategy supports many more variations.

---

## 1. Why Theming Matters

- **User preference**: reduce eye strain, save battery, match time of day.
- **Accessibility**: improve contrast for low-vision users.
- **Brand**: support white-label or multi-brand products.
- **Context**: adapt to device, environment, or mode.

---

## 2. Dark Mode Principles

### Do not just invert

Dark mode is not white text on a black background. Pure black can be harsh and cause halation. Use dark grays (e.g., `#121212`, `#1e1e1e`) for backgrounds.

### Reduce luminance in dark mode

- Avoid bright, saturated colors. They can vibrate against dark backgrounds.
- Use lower saturation for primary colors in dark mode.
- Increase contrast for text but keep it comfortable.

### Maintain hierarchy

- Use surface elevation to show hierarchy, not just shadows.
- Lighter surfaces appear closer; darker surfaces recede.
- Use overlays (e.g., `+4%` white) to create elevation.

### Color adaptation

- Background: dark surface.
- Text: high-contrast light text.
- Accents: desaturated versions of primary colors.
- Status colors: adjust for visibility (e.g., reds can become too bright).

---

## 3. Theme Architecture

### Token approach

Use semantic tokens that map to different values per theme.

```
--color-background-primary
  light: #ffffff
  dark:  #121212

--color-text-primary
  light: #1a1a1a
  dark:  #f5f5f5
```

### Theme-aware tokens

| Semantic token | Purpose |
|----------------|---------|
| `background-base` | Main app background. |
| `background-surface` | Cards, sheets, panels. |
| `background-elevated` | Floating elements. |
| `text-primary` | Headings and body. |
| `text-secondary` | Hints, captions. |
| `border-default` | Dividers and outlines. |
| `accent-primary` | Buttons, links. |
| `status-error` | Errors and warnings. |

### Token tiers

1. **Global tokens**: raw values (hex, size, etc.).
2. **Semantic tokens**: meaning-based (background, text, border).
3. **Component tokens**: specific to a component.

---

## 4. Implementing Dark Mode

### CSS custom properties

```css
:root {
  --color-background: #ffffff;
  --color-text: #1a1a1a;
}

[data-theme="dark"] {
  --color-background: #121212;
  --color-text: #f5f5f5;
}
```

### System preference

```css
@media (prefers-color-scheme: dark) {
  :root {
    --color-background: #121212;
    --color-text: #f5f5f5;
  }
}
```

### User override

- Allow users to select: light, dark, or system.
- Save the preference and respect it on return.
- Avoid flash of unstyled content by setting the theme early.

---

## 5. Theming Beyond Dark Mode

- **Brand themes**: different color schemes for different brands.
- **Seasonal themes**: temporary visual changes.
- **High contrast**: for accessibility.
- **Focus mode**: reduced visual noise.
- **Power saving mode**: darker, lower energy.

---

## 6. Common Mistakes

- Inverting colors without adjusting saturation.
- Using pure black backgrounds.
- Ignoring shadows in dark mode; use elevation overlays instead.
- Forgetting status color adjustments.
- Not testing images and media in dark mode.
- Hard-coding colors instead of using tokens.
- Not respecting `prefers-color-scheme`.

---

## 7. Checklist

- [ ] Tokens are semantic and theme-agnostic.
- [ ] Dark mode uses dark grays, not pure black.
- [ ] Saturated colors are desaturated in dark mode.
- [ ] Hierarchy is shown through elevation, not only shadows.
- [ ] Status colors are adjusted for dark surfaces.
- [ ] System preference is respected.
- [ ] Users can manually choose and save a theme.
- [ ] Images and media look good in dark mode.
- [ ] All components are tested in every theme.
- [ ] Themes are documented and consistent.
