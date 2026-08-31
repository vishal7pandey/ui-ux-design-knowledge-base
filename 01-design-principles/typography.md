# Typography for UI/UX

## The Basics

### Font Categories

| Category | Personality | Use For |
|---|---|---|
| **Serif** | Traditional, authoritative, elegant | Editorial, luxury, print-heavy |
| **Sans-serif** | Modern, clean, versatile | UI body text, most digital interfaces |
| **Monospace** | Technical, precise | Code, data, terminal-style UIs |
| **Display** | Bold, expressive | Headlines, marketing, hero sections |

### Recommendation
- **UI text:** Sans-serif (Inter, Roboto, system-ui, SF Pro)
- **Code/data:** Monospace (JetBrains Mono, Fira Code, SF Mono)
- **Editorial/brand:** Serif or display font for headlines only

## Font Size Scale

Use a modular scale (ratio-based). Common ratios: 1.125 (minor second), 1.250 (major third), 1.333 (perfect fourth).

### Recommended Scale (1.250 ratio)
```
xs:    0.64rem  (~10px)   — captions, labels
sm:    0.8rem   (~13px)   — secondary text, table cells
base:  1rem     (16px)    — body text (NEVER go below this for body)
lg:    1.25rem  (20px)    — lead text, card titles
xl:    1.563rem (25px)    — section headings
2xl:   1.953rem (31px)    — page headings
3xl:   2.441rem (39px)    — hero text
4xl:   3.052rem (49px)    — large display
```

### Minimum Sizes
- **Body text:** 16px (never smaller)
- **Secondary text:** 14px minimum
- **Labels/captions:** 12px absolute minimum
- **Touch targets:** Size matters more than font — 44×44px minimum

## Line Height (Leading)

| Context | Line Height |
|---|---|
| Body text | 1.5–1.6× font size |
| Headings | 1.2–1.3× font size |
| UI labels/buttons | 1.0–1.2× font size |
| Long-form reading | 1.6–1.8× font size |

## Letter Spacing (Tracking)

| Context | Letter Spacing |
|---|---|
| Body text | Normal (0) |
| Small text / uppercase | +0.05em to +0.1em |
| Large headings | -0.02em to -0.05em |
| All-caps labels | +0.08em |

## Font Weight

| Weight | Name | Use For |
|---|---|---|
| 400 | Regular | Body text |
| 500 | Medium | Emphasis, nav items, table headers |
| 600 | Semibold | Buttons, card titles |
| 700 | Bold | Section headings, strong emphasis |
| 800+ | Extrabold/Black | Display headings only |

> **Rule:** Don't use more than 3 weights in a UI. Regular + Medium + Bold covers 95% of needs.

## Hierarchy Through Typography

Establish clear levels. Each level should be visually distinct:

```
H1 — 2.44rem, Bold, tight leading     → Page title
H2 — 1.95rem, Bold, tight leading      → Section title
H3 — 1.56rem, Semibold, normal leading → Subsection
H4 — 1.25rem, Semibold, normal leading → Card title
Body — 1rem, Regular, 1.5 leading      → Paragraphs
Small — 0.8rem, Regular                → Metadata, captions
Label — 0.75rem, Medium, uppercase     → Form labels, tags
```

## Readability Rules

1. **Line length:** 45–75 characters per line (max 85 for comfort).
2. **Contrast:** Minimum 4.5:1 for body text (WCAG AA).
3. **Paragraph spacing:** Equal to or greater than line height.
4. **Avoid all-caps** for body text — it's harder to read and feels aggressive.
5. **Don't justify text** in digital UI — it creates uneven word spacing.
6. **Use proper quotes** — "smart quotes" not "dumb quotes".
7. **Use real ellipsis** — … not ...

## Font Pairing

### Safe Pairings
- **Inter + JetBrains Mono** — Modern tech UI
- **System UI + SF Mono** — Apple ecosystem native
- **Roboto + Roboto Mono** — Material Design
- **Georgia + Helvetica** — Editorial + clean UI
- **Playfair Display + Source Sans Pro** — Elegant + readable

### Pairing Rules
1. Contrast personalities (serif heading + sans body, or vice versa).
2. Never use two fonts from the same category (two sans-serifs compete).
3. Keep it to 2 fonts max in a UI (3 if one is monospace for code).
4. Test at small sizes — some fonts look great at 48px but terrible at 14px.

## Responsive Typography

```css
/* Use clamp() for fluid typography */
h1 {
  font-size: clamp(1.95rem, 5vw, 2.44rem);
}

body {
  font-size: clamp(1rem, 2vw, 1.125rem);
}
```

## Variable Fonts

Variable fonts allow multiple weights/styles in a single file:
- Better performance (one file vs. many).
- Smooth weight transitions for animations.
- Supported in all modern browsers.

## Typography Token Naming

```css
--font-family-sans: 'Inter', system-ui, sans-serif;
--font-family-mono: 'JetBrains Mono', monospace;

--font-size-xs: 0.75rem;
--font-size-sm: 0.875rem;
--font-size-base: 1rem;
--font-size-lg: 1.25rem;
--font-size-xl: 1.5rem;

--font-weight-regular: 400;
--font-weight-medium: 500;
--font-weight-bold: 700;

--line-height-tight: 1.25;
--line-height-normal: 1.5;
--line-height-relaxed: 1.75;
```

---

## Choosing the Right Web Font (A Practical Framework)

Font selection depends on **practical and functional** needs first — not just aesthetics. Work through these questions in order.

### 1. What's the Project's Scope?
| Scope | Recommendation |
|---|---|
| **Long-term** (product, app, publication) | Choose a **large type family** with many weights/styles/variants (small caps, ligatures). One family covers headlines, body, UI labels, and emphasis without mixing fonts. Examples: Inter, Roboto, Source Sans, Work Sans |
| **Short-term** (poster, one-off asset, logo) | A single-weight or small family is fine — you don't need the full range |

### 2. What Should the Font Say? (Familiarity vs. Distinction)
- Common/system fonts (Arial, Helvetica, Times) are safe but generic.
- There's no need to compromise today — reliable **web fonts** offer far more character than old system-font defaults.
- Uncommon/newer fonts help a product stand out but carry more risk of poor multi-script or weight support — audit before committing.

### 3. How Much Text Are You Setting? (Length Determines Category)
| Text Length | Recommended Style |
|---|---|
| **Headlines/short text** (few words) | Expressive, high-contrast, even decorative fonts — Display, Script. Use bold/compressed sans, or hairline-serif for short lines. |
| **Medium** (3–4 paragraphs) | Flexible — old-style/transitional serif (Libre Baskerville) or Humanist/Grotesque sans (Cabin, Raleway) |
| **Long-form** (5+ paragraphs) | Serif is the safer, traditional choice — Old Style/Transitional serifs (EB Garamond, Libre Baskerville) remain easy on the eyes at length |

### 4. What Point Size? (Size Changes What "Works")
| Size | Guidance |
|---|---|
| **Small (≤16pt)** | Sans-serif with tall x-height, low stroke contrast, even weight (Roboto, Montserrat, Raleway) |
| **Medium (16–24pt)** | Geometric/Grotesque/Humanist sans without extreme weights; or low-contrast slab serifs (Arvo, Sanchez, Slabo) |
| **Large/Display (24pt+)** | Nearly any genre works — decorative, script, high-contrast serifs. Avoid large counters/tall x-heights (designed for small-size legibility) since they look out of place scaled up |

> **Quality tell:** Examine the shapes of "a", "g", and numerals — these reveal how much craft went into a typeface. Risky/extravagant shapes are more acceptable in low-frequency glyphs (v, w, x, y, z) and italics.

### 5. Who's the Audience? (Language & Script Support)
- Auto-translate makes it near-certain some users will see your content in another language — if your font lacks the right glyphs, browsers silently swap fonts mid-layout (the "ransom note effect").
- Check for **Extended Latin** support (á, â, ä, å, ą) if you serve European languages.
- For Cyrillic, Greek, Arabic, Hebrew, or South/Southeast Asian scripts, verify the family has matching, harmonized characters — don't assume.
- "Superfamilies" (e.g., families with 100+ weights/scripts) are the safest bet for global products.

### 6. Functionality vs. Design Features
| Type | Examples | Purpose |
|---|---|---|
| **Functional range** | Italics, weight range (thin→black) | Core usability across contexts |
| **Design features** | Small caps, contextual alternates, numeral styles | Polish and personality — nice-to-have, not essential |

**Numeral styles matter for data-heavy UI:**
- **Oldstyle figures** — vary in height/baseline, better for reading in paragraphs
- **Tabular figures** — uniform width, vertically centered — required for tables/data grids so digits align

### 7. Font Pairing
- **Contrast** pairings (serif heading + sans body) create dynamism.
- **Similarity** pairings (same superfamily, e.g., a Sans + matching Serif variant) create cohesion.
- Never pair two fonts from the same category (two competing sans-serifs).
- Max 2 fonts in a UI (3 if one is monospace for code).
- Always test pairings at the actual sizes you'll ship — a pairing that looks great at 48px can fail at 14px.

### Font Selection Checklist
- [ ] Scope defined (long-term family vs. one-off)
- [ ] Length of text per screen considered (headline vs. long-form)
- [ ] Target point sizes tested (small/medium/large)
- [ ] Language/script coverage verified (Extended Latin, Cyrillic, etc.)
- [ ] Numeral style checked for data tables (tabular vs. oldstyle)
- [ ] Pairing tested at real, in-context sizes
- [ ] Licensing verified for web use
