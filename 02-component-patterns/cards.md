# Cards

## What Is a Card?

A card is a flexible container that groups related content and actions. It's one of the most versatile UI components — used for products, articles, profiles, dashboards, and more.

## Card Anatomy

```
┌─────────────────────────────┐
│  ┌───────────────────────┐  │
│  │      Media / Image     │  │  ← Optional: image, video, chart
│  └───────────────────────┘  │
│                             │
│  Card Title                 │  ← Title (bold, prominent)
│  Secondary text or metadata │  ← Subtitle / metadata
│                             │
│  Body content description   │  ← Description / content
│  that provides context...   │
│                             │
│  [Action]         [Action]  │  ← Optional: actions / buttons
└─────────────────────────────┘
```

## Card Types

### Basic Content Card
Image + title + description. Used for articles, blog posts, products.

### Stat / Metric Card
```
┌──────────────────┐
│  Revenue          │
│  $48,250          │  ← Big number, bold
│  ↑ 12% vs. last   │  ← Trend indicator
└──────────────────┘
```

### Profile Card
Avatar + name + role + actions. Used for team members, contacts.

### Product Card
Image + name + price + rating + add-to-cart. Used in e-commerce.

### Action Card
Icon + title + description + CTA. Used for dashboards, onboarding.

### Interactive Card
Entire card is clickable. Use hover state to indicate interactivity.

## Card Layouts

### Grid
```
┌──────┐ ┌──────┐ ┌──────┐
│ Card │ │ Card │ │ Card │
└──────┘ └──────┘ └──────┘
┌──────┐ ┌──────┐ ┌──────┐
│ Card │ │ Card │ │ Card │
└──────┘ └──────┘ └──────┘
```
- Responsive: 1 column (mobile) → 2 (tablet) → 3-4 (desktop)
- Equal gap between cards (16-24px)
- Equal card heights within a row

### List
```
┌──────────────────────────────┐
│ [img] Title    metadata  [→] │
├──────────────────────────────┤
│ [img] Title    metadata  [→] │
├──────────────────────────────┤
│ [img] Title    metadata  [→] │
└──────────────────────────────┘
```
- Horizontal layout, full width
- Good for scanning many items

### Masonry
- Variable height cards
- Pinterest-style
- Good for image-heavy content
- Use CSS columns or grid

## Card Styling

### Elevation / Shadow
| Level | Shadow | Use For |
|---|---|---|
| Flat | No shadow | Embedded cards, grouped cards |
| Low | `0 1px 3px rgba(0,0,0,0.12)` | Default cards |
| Medium | `0 4px 12px rgba(0,0,0,0.15)` | Hover state, interactive cards |
| High | `0 8px 24px rgba(0,0,0,0.18)` | Dragged card, popover |

### Border vs. Shadow
- **Border:** Subtle, clean, works in light and dark mode
- **Shadow:** Adds depth, separates from background
- **Both:** Maximum separation (use sparingly)

### Rounded Corners
- 8px–12px is the sweet spot for most cards
- 16px+ for a softer, friendlier feel
- 4px or less for a more serious/corporate feel
- Be consistent across all cards

### Padding
| Card Size | Padding |
|---|---|
| Compact | 12px–16px |
| Standard | 16px–24px |
| Comfortable | 24px–32px |

## Card Content Guidelines

### Images
- Consistent aspect ratio across all cards in a grid
- Use object-fit: cover to avoid distortion
- Provide fallback for missing images
- Lazy load images below the fold

### Titles
- 1-2 lines max, truncate with ellipsis if longer
- Bold or semibold weight
- Font size: 16px–20px

### Descriptions
- 2-3 lines max, truncate with ellipsis
- Regular weight, secondary text color
- Font size: 14px–16px

### Metadata
- Use icons + text for metadata (date, author, category)
- Smaller font size (12px–14px)
- Secondary or muted text color

### Actions
- Place at the bottom of the card
- Max 2-3 actions per card
- Primary action on the right or as full-width button
- Use icon buttons for secondary actions (bookmark, share)

## Interactive Cards

### Clickable Card
- Entire card is a link/button
- Hover: subtle shadow elevation + cursor pointer
- Focus: visible focus ring around the card
- Don't nest interactive elements inside a clickable card (use a separate link area instead)

### Card with Actions
- Card body is not clickable
- Actions are separate buttons/links at the bottom
- Each action has its own hover/focus state

### Hover States
```
Default:  low shadow, normal position
Hover:    medium shadow, slight translateY(-2px)
Active:   low shadow, translateY(0)
```

## Card Grid Behavior

### Responsive Breakpoints
```
Mobile:    1 column
Tablet:    2 columns
Desktop:   3 columns
Wide:      4 columns
```

### Equal Heights
- All cards in a row should be the same height
- Use CSS grid or flexbox with `align-items: stretch`
- Content at the bottom (actions) should align across cards

### Empty States
- Show a friendly empty state when no cards to display
- Include an illustration, message, and CTA

## Card Performance

- Lazy load images
- Virtualize long lists of cards (react-window, react-virtualized)
- Skeleton loading states for card content
- Avoid heavy shadows on large grids (performance)

## Do's and Don'ts

### Do
- Keep card content concise
- Maintain consistent sizing in grids
- Use clear hierarchy within the card
- Show loading skeletons
- Provide empty states

### Don't
- Cram too much content into a card
- Mix card styles in the same grid
- Make entire card clickable if it contains buttons
- Use different aspect ratios for images in the same grid
- Forget hover and focus states for interactive cards
