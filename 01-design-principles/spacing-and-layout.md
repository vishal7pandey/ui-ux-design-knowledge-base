# Spacing & Layout

## The 8px Grid System

Use **8px as your base unit**. All spacing values should be multiples of 8 (with 4px as the half-step for fine adjustments).

### Why 8px?
- Most screen dimensions are divisible by 8.
- Creates natural rhythm and consistency.
- Easy to reason about: "Is this 16 or 24?" not "Is this 15 or 17?"
- Design tools (Figma) snap easily to 8px grids.

### Spacing Scale
```
4px   — tight, inline spacing (icon to text)
8px   — base unit, small gaps
12px  — compact component padding
16px  — standard component padding, small section gaps
24px  — section gaps, card padding
32px  — large section gaps
48px  — page-level section separation
64px  — major section separation, hero spacing
96px  — page top/bottom padding on desktop
```

## Padding & Margin

### Component Padding
| Component Type | Padding |
|---|---|
| Buttons | 12px vertical, 24px horizontal (compact: 8px/16px) |
| Cards | 16px–24px |
| Input fields | 12px vertical, 16px horizontal |
| Modals | 24px–32px |
| Navigation bars | 16px vertical, 24px horizontal |
| List items | 12px–16px vertical |

### Section Spacing
| Context | Spacing |
|---|---|
| Between related items | 8px–16px |
| Between cards in a grid | 16px–24px |
| Between sections on a page | 32px–64px |
| Page edge padding (mobile) | 16px |
| Page edge padding (tablet) | 24px–32px |
| Page edge padding (desktop) | 32px–48px |

## Layout Grids

### 12-Column Grid (Desktop)
- **Columns:** 12
- **Gutter:** 24px (16px on tablet)
- **Margin:** 32px+ (varies by breakpoint)
- **Max content width:** 1200px–1440px

### 4-Column Grid (Mobile)
- **Columns:** 4
- **Gutter:** 16px
- **Margin:** 16px

### Breakpoints
```
Mobile:     320px – 767px    (4 columns)
Tablet:     768px – 1023px   (8 columns)
Desktop:    1024px – 1439px  (12 columns)
Wide:       1440px+          (12 columns, wider margins)
```

## Whitespace

Whitespace (negative space) is not wasted space — it's a design element.

### Functions of Whitespace
1. **Grouping:** Related items have less space between them.
2. **Separation:** Unrelated items have more space.
3. **Attention:** More whitespace around an element draws focus.
4. **Breathing room:** Prevents cognitive overload.
5. **Luxury feel:** Premium brands use generous whitespace.

### The Law of Proximity
> Objects close together are perceived as related. Objects far apart are perceived as unrelated.

**Example:**
```
[Label]                    ← too far from input
[Input field]

[Label]                    ← correct: tight spacing
[Input field]
```

## Alignment

### Rules
1. **Pick one alignment** per section — left, center, or right. Don't mix.
2. **Left-align** text content (in LTR languages). It's the most readable.
3. **Center-align** only for short headings, hero sections, or mobile-first designs.
4. **Right-align** numbers in tables and financial data for easy scanning.
5. **Align form labels** consistently — all above inputs, or all inline.

### Visual Alignment vs. Mathematical Alignment
Sometimes mathematically centered elements look off-center due to optical illusions. Trust your eye, not the pixel values. This is called **optical adjustment**.

## Z-Pattern & F-Pattern

### Z-Pattern
For pages with minimal content (landing pages, login screens):
```
Start → → → → → → → → End (logo)                    (CTA)
  ↘
    ↘
      ↘
Start → → → → → → → → End
```

### F-Pattern
For content-heavy pages (dashboards, articles, search results):
```
████████████████████████  ← top bar scanned fully
████████████████
████████████
████████████████████████  ← each row scanned left-to-right
████████████
████████████████
```

## Safe Areas & Insets

### Mobile
- **Status bar:** Top safe area (varies by device, ~44px on notched devices)
- **Home indicator:** Bottom safe area (~34px on notched devices)
- **Thumb zone:** Bottom 1/3 of screen — place primary actions here

### Desktop
- **Browser chrome:** Account for URL bar, bookmarks bar.
- **Scrollbars:** Leave room for scrollbars (typically 15-17px).

## Content Width

| Content Type | Max Width |
|---|---|
| Body text / articles | 65–75 characters (~680px) |
| Form width | 400–600px |
| Card width | 300–400px |
| Modal width | 480–640px (max 90vw) |
| Full-width banners | 100% with max 1440px content |
