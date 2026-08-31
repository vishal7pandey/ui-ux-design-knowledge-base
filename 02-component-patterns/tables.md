# Tables & Data Grids

## When to Use Tables

- **Structured data** with multiple attributes per row
- **Comparison** of items across multiple dimensions
- **Sorting, filtering, searching** large datasets
- **Bulk operations** on multiple records

### When NOT to Use Tables
- Single attribute per item → use a list
- Visual comparison → use cards or charts
- Hierarchical data → use a tree view
- Timeline data → use a timeline component

## Table Anatomy

```
┌──┬───────────┬───────────┬───────────┬──────────┐
│  │ Column A  │ Column B  │ Column C  │ Actions  │  ← Header row
├──┼───────────┼───────────┼───────────┼──────────┤
│☐ │ Data      │ Data      │ Data      │ [⋯]     │  ← Data row
├──┼───────────┼───────────┼───────────┼──────────┤
│☐ │ Data      │ Data      │ Data      │ [⋯]     │  ← Data row
└──┴───────────┴───────────┴───────────┴──────────┘
   ← Checkbox   ← Sortable headers    ← Row actions
```

## Table Types

### Basic Table
Static data, no interactions. Good for small datasets (< 20 rows).

### Data Grid
Interactive table with sorting, filtering, pagination, and selection. For large datasets.

### Editable Table
Cells can be edited inline. Common in spreadsheets and admin panels.

### Tree Table
Rows can expand to show nested/child rows.

### Responsive Table
Adapts to screen size — may transform to cards on mobile.

## Column Design

### Column Width
- **Fixed width:** For icons, actions, short data (status, date)
- **Flexible width:** For text content that varies in length
- **Min/max width:** Prevent columns from getting too narrow or too wide
- **Right-align:** Numbers, currency, percentages
- **Left-align:** Text, names, descriptions
- **Center-align:** Icons, status badges, checkboxes

### Column Ordering
1. **Selection column** (checkbox) — first, if needed
2. **Primary identifier** — name, title, ID
3. **Key attributes** — most important columns next
4. **Secondary attributes** — less critical data
5. **Actions** — last column

### Column Visibility
- Allow users to show/hide columns for wide tables
- Remember user preferences
- Provide a "Reset to default" option

## Sorting

### Guidelines
- Click column header to sort
- Show sort direction indicator (▲ / ▼)
- Toggle ascending/descending on repeated clicks
- Third click returns to default order (optional)
- Multi-column sort for advanced use cases (Shift+click)

### Sortable Header
```
  Name ▲    ← currently sorted ascending
  Date      ← not sorted, clickable
  Status    ← not sorted, clickable
```

## Filtering

### Filter Types
| Type | UI Element | Use Case |
|---|---|---|
| Text search | Input field | Search across all columns |
| Dropdown | Select | Filter by specific column value |
| Date range | Date pickers | Filter by date range |
| Checkbox | Checkbox group | Multi-select filter |
| Range slider | Slider | Filter by numeric range |

### Filter UI
- Place filters above the table
- Show active filter count
- "Clear all filters" button
- Apply filters immediately (or on button click for complex filters)
- Show result count after filtering

## Pagination vs. Virtual Scrolling

### Pagination
```
  Showing 1-10 of 247    [←] [1] 2 3 4 5 [→]
```
- Predictable, accessible, deep-linkable
- User can estimate total data size
- Good for SEO (each page has a URL)

### Virtual Scrolling
- Renders only visible rows + buffer
- Smooth scrolling experience
- Good for 1000+ rows
- No page reloads
- Harder to deep-link

### Load More
```
  [    Load 10 more rows    ]
```
- Simple, maintains scroll position
- Good for moderate datasets
- Can cause memory issues with very large datasets

## Row Selection

### Single Selection
- Click row to select
- Highlight selected row
- Show details in a side panel or expand row

### Multi Selection
- Checkbox column (first column)
- "Select all" checkbox in header
- Show count of selected rows
- Bulk actions appear when rows are selected

```
┌──┬───────────┬───────────┐
│☐✓│ Name      │ Status    │  ← select all (checked)
├──┼───────────┼───────────┤
│☑ │ Alice     │ Active    │
│☑ │ Bob       │ Inactive  │
│☐ │ Charlie   │ Active    │
└──┴───────────┴───────────┘
  2 of 247 selected  [Delete] [Export]
```

## Row Actions

### Inline Actions
- Show on row hover (desktop) or always visible (mobile)
- Max 2-3 visible actions
- Use icon buttons to save space
- Overflow menu (⋯) for additional actions

### Row Click Behavior
- **Navigate to detail page** — most common
- **Expand row** — show more details inline
- **Toggle selection** — if using row-click selection
- Don't mix row-click navigation with row-click selection

## Empty States

```
┌───────────────────────────────────┐
│                                   │
│         📭                         │
│     No records found               │
│                                   │
│  Try adjusting your filters or    │
│  create a new record.             │
│                                   │
│       [Create Record]             │
└───────────────────────────────────┘
```

- Show illustration or icon
- Clear message explaining why it's empty
- CTA to take action (create, import, adjust filters)

## Loading States

### Skeleton Loading
- Show skeleton rows while data loads
- Match the expected row height
- Animate with shimmer effect

### Inline Loading
- Show spinner in the table area
- Don't block the entire page
- Keep filter/search controls enabled

## Responsive Tables

### Scroll Horizontally
- On mobile, allow horizontal scroll
- Keep the first column (identifier) sticky
- Show scroll indicator

### Transform to Cards
```
Mobile:
┌───────────────────┐
│ Alice              │
│ Status: Active     │
│ Role: Admin        │
│ [View] [Edit]      │
└───────────────────┘
┌───────────────────┐
│ Bob                │
│ Status: Inactive   │
│ Role: User         │
│ [View] [Edit]      │
└───────────────────┘
```

### Hide Less Important Columns
- Prioritize columns for mobile view
- Hide secondary columns on small screens
- Allow user to expand for full details

## Dense vs. Comfortable

| Mode | Row Height | Use Case |
|---|---|---|
| Compact | 32px | Data-heavy admin panels, power users |
| Standard | 40px | Default, most use cases |
| Comfortable | 56px | Mobile, touch-friendly, casual users |

## Do's and Don'ts

### Do
- Right-align numbers for easy comparison
- Allow column resizing for flexible layouts
- Show total count and visible range
- Provide sorting on meaningful columns
- Use sticky headers for long tables
- Handle empty and loading states

### Don't
- Display too many columns (consider hiding some)
- Use tables for layout (use CSS grid/flexbox)
- Forget responsive behavior
- Make rows too tall on desktop or too short on mobile
- Mix row-click selection with row-click navigation
- Put important data in horizontally scrolled columns
