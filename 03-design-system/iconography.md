# Iconography

## Why Icons Matter

Icons communicate meaning quickly, transcend language barriers, and save space. But poorly chosen icons confuse users. Choose wisely.

## Icon Styles

| Style | Description | Best For |
|---|---|---|
| **Outline / Line** | Thin strokes, no fill | Modern, clean UIs; default choice |
| **Filled / Solid** | Solid shapes | Active states, dense UIs, mobile |
| **Duotone** | Two-tone with opacity | Friendly, distinctive branding |
| **Glyph** | Single-color simple shapes | Utility, system UIs |
| **3D / Illustrative** | Detailed, colorful | Marketing, empty states, onboarding |

### Consistency Rules
- **Pick one style** and stick with it across the entire product
- Don't mix outline and filled icons (except for active/inactive states)
- Use the same icon family/set (same designer or library)
- Consistent stroke width (1.5px or 2px for outline icons)

## Icon Sizing

| Size | Use Case |
|---|---|
| 12px | Inline with small text, badges |
| 16px | Default UI, buttons, form elements |
| 20px | Navigation, cards, medium UI elements |
| 24px | Large buttons, headers, mobile nav |
| 32px | Empty states, feature highlights |
| 48px+ | Illustrations, onboarding |

### Rules
- Icons should align to the same grid (usually 24×24 viewBox)
- Optical alignment: some icons need slight adjustment to look centered
- Maintain consistent visual weight across different icons

## Icon Libraries

### Recommended Open Source Libraries
| Library | Style | License | Notes |
|---|---|---|---|
| [Lucide](https://lucide.dev/) | Outline | ISC | 1000+ icons, fork of Feather, highly recommended |
| [Phosphor](https://phosphoricons.com/) | Multiple | MIT | 6 weights, 1200+ icons |
| [Heroicons](https://heroicons.com/) | Outline + Solid | MIT | By Tailwind team, 300+ icons |
| [Tabler Icons](https://tabler-icons.io/) | Outline | MIT | 4000+ icons, consistent stroke |
| [Feather](https://feathericons.com/) | Outline | MIT | 280+ icons, classic clean set |
| [Bootstrap Icons](https://icons.getbootstrap.com/) | Mixed | MIT | 2000+ icons |
| [Material Symbols](https://fonts.google.com/icons) | Variable | Apache 2.0 | Google's icon system |
| [Remix Icon](https://remixicon.com/) | Mixed | Apache 2.0 | 2700+ icons |
| [Octicons](https://primer.style/foundations/icons/) | Outline | MIT | GitHub's icon set |

### Choosing a Library
1. **Coverage:** Does it have all the icons you need?
2. **Consistency:** Same visual style, stroke width, corner radius?
3. **Customizable:** Can you adjust size, color, stroke?
4. **Bundle size:** Tree-shakeable? SVG or icon font?
5. **License:** Compatible with your project?
6. **Maintenance:** Actively maintained?

## SVG vs. Icon Fonts

### SVG (Recommended)
```
✓ Crisp at any size
✓ Styleable with CSS (color, stroke, fill)
✓ Tree-shakeable (only include what you use)
✓ Accessible (inline SVG with aria labels)
✗ More markup per icon
```

### Icon Fonts
```
✓ Easy to use (just add a class)
✓ Single file load
✗ Not as crisp at all sizes
✗ Harder to style (limited to font properties)
✗ Accessibility challenges
✗ Can't tree-shake
```

## SVG Best Practices

### Inline SVG
```html
<svg
  width="20"
  height="20"
  viewBox="0 0 24 24"
  fill="none"
  stroke="currentColor"
  stroke-width="2"
  stroke-linecap="round"
  stroke-linejoin="round"
  aria-hidden="true"
  class="icon"
>
  <path d="M12 5v14M5 12h14" />
</svg>
```

### Key Attributes
- `viewBox="0 0 24 24"` — standard 24px grid
- `fill="none"` — for outline icons (use stroke)
- `stroke="currentColor"` — inherit color from CSS
- `stroke-width="2"` — consistent stroke weight
- `stroke-linecap="round"` — rounded line ends
- `stroke-linejoin="round"` — rounded corners
- `aria-hidden="true"` — hide from screen readers (when decorative)

### Using `currentColor`
```css
.icon { color: var(--color-text-primary); }
.button:hover .icon { color: var(--color-primary); }
```
This lets you control icon color via CSS without modifying the SVG.

## Accessibility

### Decorative Icons
Icons that accompany text labels don't need to be announced:
```html
<button>
  <svg aria-hidden="true">...</svg>
  <span>Settings</span>
</button>
```

### Standalone Icons
Icons without text labels need accessible names:
```html
<!-- Method 1: aria-label on button -->
<button aria-label="Settings">
  <svg aria-hidden="true">...</svg>
</button>

<!-- Method 2: title in SVG -->
<button>
  <svg role="img" aria-labelledby="icon-title">
    <title id="icon-title">Settings</title>
    <path d="..." />
  </svg>
</button>
```

### Meaningful Icons
If the icon conveys information not available elsewhere:
```html
<svg role="img" aria-label="Required field">
  <path d="..." />
</svg>
```

## Icon + Text Combination

### Alignment
- Icon vertically centered with text
- Gap between icon and text: 8px (or 6px for compact UI)
- Icon size matches text size: 16px icon with 16px text, 20px icon with 20px text

### Position
- **Leading (left):** Icon before text (most common)
  - `[⚙ Settings]`
- **Trailing (right):** Icon after text
  - `[Next →]`
- **Be consistent:** Don't mix leading and trailing in the same context

## Custom Icons

### When to Create Custom Icons
- Your product needs a unique icon not in any library
- Brand-specific concepts (logo, mascot, product icons)
- Domain-specific actions (e.g., medical, financial)

### Custom Icon Guidelines
1. **Match your library's style** (stroke width, corner radius, grid)
2. **Use the same 24×24 viewBox**
3. **Test at small sizes** (16px) — simplify if needed
4. **Optical balance** — geometric center ≠ visual center
5. **Keep it simple** — 2-3 elements max per icon
6. **Test in context** — check against background, next to other icons

## Icon Naming Conventions

```
kebab-case:      settings, arrow-left, chevron-down, mail-open
```

### Naming Patterns
| Pattern | Example | Meaning |
|---|---|---|
| `{noun}` | `home`, `mail`, `user` | Basic icon |
| `{noun}-{modifier}` | `mail-open`, `user-plus` | Variant |
| `{action}-{noun}` | `add-folder`, `edit-pencil` | Action on object |
| `{direction}` | `arrow-left`, `chevron-up` | Directional |
| `{noun}-{state}` | `bell-off`, `eye-off` | State toggle |

## Do's and Don'ts

### Do
- Use icons from a consistent library
- Pair icons with text labels for clarity
- Use `currentColor` for easy theming
- Provide aria-labels for standalone icons
- Test icons at all sizes you'll use
- Use SVG over icon fonts

### Don't
- Mix icon styles (outline + filled) randomly
- Use icons that could be confused for different meanings
- Rely on icons alone for critical actions
- Stretch icons non-proportionally
- Use copyrighted icons without permission
- Use emoji as UI icons (rendering varies across platforms)
