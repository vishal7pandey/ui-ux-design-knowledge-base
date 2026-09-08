# Color Palettes, Contrast & Modern Color Spaces

This guide complements the existing `color-theory.md` and `visual-hierarchy.md` with production-ready palette templates, modern contrast standards (APCA, OKLCH), and practical formulas that let you stop reinventing color decisions.

---

## 1. Modern Color Space: OKLCH

### Why move beyond HSL/HEX

`HSL` is familiar but **perceptually broken**. `hsl(60 100% 50%)` (yellow) and `hsl(240 100% 50%)` (blue) share the same "lightness" value, yet yellow looks far brighter than blue. That makes consistent scales, gradients, hover states, and dark-mode mirrors hard to maintain.

`OKLCH` (Lightness, Chroma, Hue) is perceptually uniform. Two colors with the same `L` value look equally bright across every hue.

### Format

```css
.example {
  color: oklch(0.60 0.20 250); /* oklch(L C H) */
}
```

- **L** (lightness): `0` to `1` (or `0%` to `100%`)
- **C** (chroma): `0` to `0.4` (approximate sRGB ceiling; higher for P3)
- **H** (hue): `0` to `360` degrees

### Benefits for UI

- **Consistent ramps**: 12-step scales by sweeping `L` from `0.95` to `0.15` produce usable shades for any hue.
- **Smooth gradients**: `linear-gradient(in oklch, ...)`, `color-mix(in oklch, ...)` avoid muddy midpoints.
- **Predictable contrast**: Equal `L` values → similar perceived luminance → more reliable a11y checks.
- **Wide-gamut ready**: P3 colors with sRGB fallbacks.

### Browser support

Supported in Chrome/Edge 111+, Firefox 113+, Safari 15.4+ (2022–2023). For older browsers, OKLCH declarations are ignored; provide a fallback:

```css
:root {
  --primary: #3b82f6;
  --primary: oklch(0.62 0.20 255);
}
```

---

## 2. Building a Production-Ready Palette

### The 5-role model

Most professional SaaS/dashboard palettes need exactly five core roles:

| Role | Purpose |
|------|---------|
| **Primary** | Brand, main CTAs, active nav |
| **Secondary** | Charts, secondary stats, icons |
| **Accent** | Alerts, urgent CTAs, trend indicators |
| **Background** | Page and card surfaces |
| **Text** | Body and label text |

Add **5–7 neutrals** for structure (background, surface, border, body text, muted text), and **4 semantic colors** (success, warning, error, info).

### Recommended palette size

- **5–7 neutrals** carrying UI structure
- **1 primary accent** with 5–8 lighter/darker variants
- **1–2 secondary accents** max per page
- **4 semantic colors** (each with 3–5 variants)
- **4–6 data/chart colors**

> **Rule of thumb**: Never more than **three accent colors on the same page**. Anything beyond cancels itself out.

---

## 3. Ready-to-Use Palette Templates

All values are provided in HEX and OKLCH. Choose one, then adapt to your brand hue.

### 3.1 SaaS / Admin Dashboard (Classic Blue)

A safe, high-trust palette that works for dashboards, admin panels, and B2B tools.

| Token | HEX | OKLCH | Usage |
|-------|-----|-------|-------|
| `--primary` | `#1e40af` | `oklch(0.45 0.20 264)` | Sidebar, active nav, primary buttons |
| `--primary-foreground` | `#ffffff` | `oklch(1 0 0)` | Text on primary |
| `--secondary` | `#3b82f6` | `oklch(0.62 0.20 255)` | Charts, secondary stats, links |
| `--accent` | `#f59e0b` | `oklch(0.77 0.16 70)` | Alerts, CTA highlights, warnings |
| `--background` | `#f8fafc` | `oklch(0.97 0.005 255)` | Page canvas |
| `--foreground` | `#1e293b` | `oklch(0.28 0.03 255)` | Primary text |
| `--muted` | `#64748b` | `oklch(0.55 0.03 255)` | Secondary text, icons |
| `--border` | `#e2e8f0` | `oklch(0.90 0.02 255)` | Dividers, card borders |

### 3.2 Midnight / Developer Tool

Calm, low-luminance dark palette for code tools, dashboards, and power-user apps.

| Token | HEX | OKLCH | Usage |
|-------|-----|-------|-------|
| `--primary` | `#cba6f7` | `oklch(0.77 0.14 305)` | Accent highlights, active states |
| `--primary-foreground` | `#1e1e2e` | `oklch(0.23 0.03 300)` | Text on primary (dark) |
| `--secondary` | `#89b4fa` | `oklch(0.77 0.12 260)` | Links, code tokens, charts |
| `--accent` | `#f38ba8` | `oklch(0.73 0.14 15)` | Errors, important actions |
| `--background` | `#1e1e2e` | `oklch(0.23 0.03 300)` | Page background |
| `--card` | `#313244` | `oklch(0.34 0.04 300)` | Card surfaces |
| `--foreground` | `#cdd6f4` | `oklch(0.88 0.04 270)` | Primary text |
| `--muted` | `#6c7086` | `oklch(0.55 0.04 285)` | Secondary text |
| `--border` | `#45475a` | `oklch(0.42 0.04 300)` | Dividers |

### 3.3 Minimal / Editorial

Crisp, content-first palette for blogs, docs, and clean marketing sites.

| Token | HEX | OKLCH | Usage |
|-------|-----|-------|-------|
| `--primary` | `#111827` | `oklch(0.20 0.02 260)` | Primary text, headings |
| `--primary-foreground` | `#ffffff` | `oklch(1 0 0)` | Buttons on dark |
| `--secondary` | `#374151` | `oklch(0.35 0.02 255)` | Secondary text |
| `--accent` | `#2563eb` | `oklch(0.55 0.22 265)` | Links, CTAs, focus rings |
| `--background` | `#ffffff` | `oklch(1 0 0)` | Page canvas |
| `--muted` | `#9ca3af` | `oklch(0.70 0.02 255)` | Captions, disabled |
| `--border` | `#e5e7eb` | `oklch(0.91 0.01 255)` | Dividers |

### 3.4 Nature / Wellness

Soft, organic palette for health, wellness, sustainability, and lifestyle products.

| Token | HEX | OKLCH | Usage |
|-------|-----|-------|-------|
| `--primary` | `#065f46` | `oklch(0.42 0.11 165)` | Primary actions, nav |
| `--primary-foreground` | `#ffffff` | `oklch(1 0 0)` | Text on primary |
| `--secondary` | `#10b981` | `oklch(0.72 0.19 160)` | Success, positive trends |
| `--accent` | `#f59e0b` | `oklch(0.77 0.16 70)` | Warnings, attention |
| `--background` | `#f0fdf4` | `oklch(0.97 0.04 150)` | Light page canvas |
| `--foreground` | `#064e3b` | `oklch(0.30 0.08 165)` | Primary text |
| `--muted` | `#059669` | `oklch(0.55 0.15 165)` | Secondary text |
| `--border` | `#d1fae5` | `oklch(0.92 0.06 155)` | Dividers |

### 3.5 Neo-Brutalism

Bold, saturated palette with high-impact borders and shadows. Use sparingly for portfolio, creative, or youth brands.

| Token | HEX | OKLCH | Usage |
|-------|-----|-------|-------|
| `--primary` | `#ff2d9d` | `oklch(0.65 0.30 345)` | Primary actions |
| `--secondary` | `#0dd9f5` | `oklch(0.80 0.17 200)` | Secondary accents |
| `--background` | `#f8f9fc` | `oklch(0.97 0.01 260)` | Page canvas |
| `--card` | `#ffffff` | `oklch(1 0 0)` | Cards |
| `--foreground` | `#111111` | `oklch(0.18 0 0)` | Text |
| `--border` | `#111111` | `oklch(0.18 0 0)` | Strong card borders |
| `--shadow` | `#111111` | `oklch(0.18 0 0)` | Offset shadows |

---

## 4. Contrast: Beyond WCAG 2.1

### WCAG 2.1 recap (still required today)

- Normal text: minimum **4.5:1**
- Large text (18pt+ or 14pt+ bold): **3:1**
- UI components / icons: **3:1** (WCAG 2.1 SC 1.4.11)

### Why APCA is the emerging standard

WCAG 2.x contrast math is a simple luminance ratio. It **overstates** contrast near black and **understates** contrast for mid-tones, making it unreliable in dark mode.

**APCA (Accessible Perceptual Contrast Algorithm)** is the proposed replacement for WCAG 3. It models how humans actually perceive contrast, accounts for text weight and size, and is far more accurate for dark mode and thin fonts.

### APCA levels (Bronze simple mode)

| Lc value | Meaning |
|----------|---------|
| **90** | Preferred for fluent body text (14px/400 min) |
| **75** | Minimum for body text, large text where readability is important |
| **60** | Minimum for content text that is not body/column text |
| **45** | Minimum for large, bold text or spot-reading |
| **30** | Minimum for non-text objects, icons, disabled text |
| **15** | Near invisibility for many users; use for decorative only |

### Practical APCA workflow

1. Design in OKLCH.
2. Use an APCA-aware contrast tool (e.g., `ui-color-palette.com`, `myndex.com/APCA`, `apca-w3` npm).
3. Check body text at **Lc 90** preferred, **75** minimum.
4. Check captions / secondary text at **Lc 60** minimum.
5. Check icons, borders, disabled states at **Lc 30+**.

### Contrast hierarchy

Design with three contrast tiers for visual hierarchy:

| Tier | Opacity/Contrast | Example |
|------|------------------|---------|
| **Primary** | Full contrast, 85–100% | Headings, primary CTAs |
| **Secondary** | 60–75% | Body text, icons, captions |
| **Tertiary** | 35–50% | Timestamps, dividers, disabled |

> **Pro tip**: If your design still reads correctly in grayscale, the hierarchy is built on the right signals (size, weight, contrast) instead of relying on color alone.

---

## 5. Dark-Mode Considerations

- **Do not just invert**. Reduce chroma in light and dark extremes to avoid neon edges and muddy darks.
- **Use pure white or near-white text** on dark backgrounds (`#ffffff` or `oklch(0.97 ...)`). Medium gray text on dark is the #1 dark-mode readability failure.
- **Surfaces should be distinguishable**: use subtle lightness steps (`+0.03` to `+0.06` L per elevation).
- **Test with APCA**, not only WCAG 2.x, because WCAG 2.x fails for dark mode.

---

## 6. Common Mistakes

1. **Using raw hex values directly** instead of semantic tokens.
2. **Changing button colors page by page** based on mood or campaigns.
3. **Ignoring disabled/focus states** until development.
4. **A palette that works in Figma but fails in dark mode**.
5. **Too many accent colors** on one page (visual hierarchy collapses).
6. **Trusting HSL lightness** to build balanced multi-hue palettes.

---

## 7. Quick Checklist

- [ ] Roles defined: primary, secondary, accent, background, text, neutrals, semantic, data
- [ ] 5–7 neutrals carry layout structure and text
- [ ] Primary accent has 5–8 lighter/darker variants for states
- [ ] Contrast tested for body text, large text, icons, components
- [ ] Light and dark modes share roles, different values
- [ ] OKLCH used for scale generation; HEX/HSL only for backwards compatibility
- [ ] APCA checked for dark mode and thin fonts
- [ ] No more than 3 accent colors per page
