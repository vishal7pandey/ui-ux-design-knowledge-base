# Navigation

## Navigation Types

### 1. Primary Navigation
The main way to move between top-level sections of your app.

| Pattern | Platform | Use Case |
|---|---|---|
| Top nav bar | Desktop | 3-7 top-level destinations |
| Bottom tab bar | Mobile | 3-5 top-level destinations |
| Side nav / sidebar | Desktop | 5+ destinations, deep hierarchy |
| Hamburger menu | Mobile | Secondary navigation, complex apps |

### 2. Secondary Navigation
Navigating within a section.

| Pattern | Use Case |
|---|---|
| Tabs | Switch between views within a page |
| Breadcrumbs | Show location in hierarchy, navigate up |
| Sub-navigation | Filter or sort within a section |

### 3. Tertiary Navigation
In-page navigation and utilities.

| Pattern | Use Case |
|---|---|
| Pagination | Navigate through paginated lists |
| In-page anchors | Jump to sections within a long page |
| Back button | Return to previous page |
| Search | Find specific content |

## Top Navigation Bar

```
┌────────────────────────────────────────────────────┐
│  Logo    Home  Products  Pricing  About    [Search] [Sign In] │
└────────────────────────────────────────────────────┘
```

### Guidelines
- Logo on the left (clickable → home)
- Nav items centered or left-aligned after logo
- Utility actions (search, sign in) on the right
- Max 7 top-level items
- Highlight current page/section
- Sticky on scroll for easy access
- Collapse to hamburger on mobile (< 768px)

### Responsive Behavior
```
Desktop:  Logo | Home | Products | Pricing | About | [Search] [Sign In]
Tablet:   Logo | Home | Products | About | [Search] [Sign In]
Mobile:   Logo |                              [☰] [Sign In]
```

## Bottom Tab Bar (Mobile)

```
┌──────────────────────────────────────┐
│                                      │
│           Content area               │
│                                      │
├──────┬──────┬──────┬──────┬──────────┤
│  🏠  │  🔍  │  ➕  │  🔔  │  👤      │
│ Home │Search│ New  │Alerts│ Profile  │
└──────┴──────┴──────┴──────┴──────────┘
```

### Guidelines
- 3-5 tabs maximum
- Icon + label (labels improve usability significantly)
- Active tab: filled icon + brand color + label visible
- Inactive tab: outline icon + muted color
- Fixed at bottom, always visible
- Safe area aware (respect home indicator)
- 48-56px height (plus safe area)

### Center Action Button
- Special elevated button in the center
- Used for primary creation action (new post, new message)
- Breaks the tab bar visually

## Sidebar Navigation

```
┌─────────┬──────────────────────────┐
│  Logo   │                          │
│         │                          │
│  ▸ Dash │     Main content         │
│  ▸ Proj │                          │
│  ▸ Team │                          │
│  ▸ Set  │                          │
│         │                          │
│  User   │                          │
└─────────┴──────────────────────────┘
```

### Guidelines
- Width: 240px–280px (expanded), 64px–72px (collapsed)
- Collapsible with toggle button
- Show icons + labels when expanded
- Show icons only when collapsed (tooltip on hover)
- Group items with section labels
- Active item: highlighted background + left border accent
- Footer area: user profile, settings
- Can be fixed or drawer-style on mobile

### Multi-Level Sidebar
```
  ▸ Dashboard
  ▸ Projects
    ├─ Active
    ├─ Archived
    └─ Templates
  ▸ Team
  ▸ Settings
```
- Expand/collapse with smooth animation
- Show nested items indented
- Remember expanded state

## Hamburger Menu

### Guidelines
- Use on mobile when you have too many items for a bottom bar
- Don't hide critical navigation behind hamburger on desktop
- Left or right side drawer
- Overlay with scrim (dimmed background)
- Swipe-to-open on mobile
- Close on outside tap or Esc key
- Animate slide-in from the edge

### When to Use
- Mobile apps with 5+ top-level destinations
- Secondary navigation items
- Settings and account options

### When NOT to Use
- If you only have 3-5 items (use bottom tabs instead)
- On desktop (use a top nav or sidebar)
- For primary actions (those should be visible)

## Breadcrumbs

```
  Home > Projects > Website Redesign > Tasks
```

### Guidelines
- Show current page hierarchy
- Last item is the current page (not a link)
- Separator: `>`, `/`, or `→`
- Truncate long paths: `Home > ... > Tasks`
- Place below the header or above the page title
- Don't use for single-level navigation

## Tabs

```
  ┌──────────┬──────────┬──────────┐
  │  Active  │  Tab 2   │  Tab 3   │
  ───────────────────────────────────
  │                                  │
  │  Tab content goes here           │
  │                                  │
  └──────────────────────────────────┘
```

### Guidelines
- 2-6 tabs per tab bar
- Active tab: underline or filled background
- Inactive tab: text only, muted color
- Don't use tabs for navigation between pages (use nav instead)
- Tabs should be at the top of the content area
- Swipeable on mobile
- Remember active tab on back navigation

### Tab Types
| Type | Style | Use Case |
|---|---|---|
| Underline | Bottom border indicator | Default, clean look |
| Filled | Background fill on active | Bold, high contrast |
| Pill | Rounded pill background | Playful, modern |
| Icon + label | Icon above text | Space-constrained |

## Pagination

```
  ←  Previous  [1] 2  3  4  5  Next  →
```

### Guidelines
- Show current page clearly
- Provide Previous/Next buttons
- Show page numbers with current highlighted
- For many pages: `1 2 3 ... 8 9 10`
- Alternative: "Load more" button or infinite scroll
- Show total count if available ("Showing 1-10 of 247")

### Load More vs. Infinite Scroll
| Pattern | Pros | Cons |
|---|---|---|
| Pagination | Control, accessible, deep-linkable | Extra clicks |
| Load More | Simple, maintains scroll position | No page numbers |
| Infinite Scroll | Seamless, addictive | Hard to reach footer, no end |

## Navigation Best Practices

### Current Page Indicator
- Always show where the user is in the navigation
- Use `aria-current="page"` for accessibility
- Visual: highlight, bold, underline, or background fill

### Keyboard Navigation
- All nav items must be keyboard accessible
- Logical tab order
- Sub-menus: arrow keys to navigate, Esc to close
- Skip link to bypass navigation

### Search
- Always provide search for content-heavy sites
- Search icon in nav bar, expands to input on click
- Search results page with filters
- Recent searches and suggestions

### Icons in Navigation
- Pair icons with labels for clarity
- Icon-only navigation needs tooltips and aria-labels
- Use consistent icon style (filled or outlined, not mixed)

### Navigation Labels
- Short and clear: "Products" not "Our Product Catalog"
- User-centered language: "My Orders" not "Order Management"
- Consistent: don't mix "Home" and "Dashboard" for the same thing
- Avoid jargon and acronyms
