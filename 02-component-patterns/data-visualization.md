# Data Visualization

## Chart Types

### When to Use Each Chart

| Chart Type | Best For | Example |
|---|---|---|
| **Line** | Trends over time | Revenue by month |
| **Bar** | Comparing categories | Sales by region |
| **Column** | Comparing categories (vertical) | Quarterly results |
| **Pie / Donut** | Parts of a whole (max 5 segments) | Market share |
| **Area** | Volume over time | Cumulative users |
| **Scatter** | Correlation between 2 variables | Price vs. rating |
| **Heatmap** | Density / intensity across 2 dimensions | Activity by day/hour |
| **Funnel** | Stages of a process | Conversion funnel |
| **Gauge** | Single value within a range | Goal progress |
| **Sparkline** | Mini trend in a small space | Table cell trend |
| **Treemap** | Hierarchical proportions | Budget breakdown |
| **Stacked bar** | Part-to-whole across categories | Revenue by product by quarter |

## Design Principles

### 1. Clarity Over Decoration
- Remove chart junk: 3D effects, gradients, shadows, unnecessary grid lines
- Every element should serve a purpose
- "Above all else show the data" — Edward Tufte

### 2. Start Y-Axis at Zero
- Bar and column charts must start at zero
- Starting at a non-zero value misleads
- Line charts can start at non-zero if the context is clear

### 3. Limit Categories
- Pie/donut: Max 5 segments (group small ones as "Other")
- Bar chart: Max 15 bars (consider grouping or pagination)
- Line chart: Max 4-5 lines (more becomes unreadable)

### 4. Use Color Purposefully
- One color for the main data series
- Muted/gray for comparison or context series
- Semantic colors for positive/negative (green/red)
- Don't use rainbow palettes for sequential data

### 5. Label Directly
- Label data points directly when possible (instead of legends)
- Place labels on or near the data
- Use legends only when direct labeling isn't feasible

## Line Charts

```
    │
 100│         ╱╲
  80│      ╱╲╱  ╲    ╱
  60│   ╱╲╱      ╲╱╲╱
  40│  ╱
  20│╱
   0└──────────────────
     Jan  Feb  Mar  Apr  May
```

### Guidelines
- 2-4px line thickness
- Smooth or angular lines (be consistent)
- Distinguish multiple lines by color, not just line style
- Show data points (dots) on hover or for sparse data
- Animate line drawing on load (left to right)
- Highlight the line the user hovers over (dim others)

### Multi-Line
- Use distinct, accessible colors
- Direct labels at the end of each line
- Interactive legend: click to toggle visibility
- Max 4-5 lines before it gets cluttered

## Bar / Column Charts

```
    │
 100│  ┌─┐
  80│  │ │ ┌─┐
  60│  │ │ │ │ ┌─┐
  40│  │ │ │ │ │ │ ┌─┐
  20│  │ │ │ │ │ │ │ │
   0└──┴─┴─┴─┴─┴─┴─┴─┴──
      A   B   C   D   E
```

### Guidelines
- Bars should be wider than the gap between them (2:1 ratio)
- Sort bars by value (descending) for non-ordinal data
- Keep ordinal data in natural order (time, age groups)
- Use consistent colors (or one accent color for the highlight bar)
- Show value on hover (tooltip) or on top of bar
- Rounded corners: 2-4px on top only

### Stacked Bars
```
    │
 100│  ███
  80│  ███ ███
  60│  ███ ███ ███
  40│  ███ ███ ███
  20│  ███ ███ ███
   0└──────────────
       A    B    C
```
- Show part-to-whole relationship
- Limit to 3-4 segments per bar
- Use a consistent color order (largest at bottom)
- Consider a legend or direct labels

## Pie / Donut Charts

### Guidelines
- Use sparingly — bar charts are usually better for comparison
- Max 5 segments (group small ones as "Other")
- Sort segments by size (largest first, clockwise from 12 o'clock)
- Donut chart is preferred (center can show total or label)
- Show percentage and value on hover
- Use distinct colors, not shades of one color

### When to Use Pie/Donut
- Showing a single part-to-whole relationship
- 2-5 segments
- The "whole" is meaningful
- Quick visual, not precise comparison

### When NOT to Use
- Comparing multiple datasets
- More than 5 segments
- Precise value reading is needed
- Segments are very similar in size

## Tooltips

```
  ┌─────────────────────┐
  │  March 2024          │
  │  Revenue: $48,250    │
  │  ↑ 12% vs. February  │
  └─────────────────────┘
```

### Guidelines
- Show on hover (desktop) or tap (mobile)
- Display: label, value, and context (comparison, percentage)
- Position near the data point, don't cover it
- Don't move with the mouse (stable position)
- Style as a small card with shadow
- Dismiss on mouse leave or tap away

## Axes & Grid

### Axis Labels
- Show on both axes
- Rotate if too long (45° or vertical)
- Abbreviate large numbers: 1K, 1M, 1B
- Use consistent formatting

### Grid Lines
- Horizontal grid lines: yes (helps read values)
- Vertical grid lines: optional (for bar charts)
- Light gray, 1px, dashed or solid
- Don't overpower the data

### Formatting
- Currency: $48,250 (not $48250)
- Large numbers: 1.2M (not 1,200,000)
- Percentages: 45% (not 0.45)
- Dates: Mar 2024 (not 2024-03-01 in UI)
- Consistent decimal places

## Legends

### Guidelines
- Place legend above or below the chart (not floating)
- Use color swatches matching the chart
- Interactive: click to toggle series visibility
- Direct labels on data are better than legends
- Keep legend items in the same order as the data

## Responsive Charts

### Mobile Adaptations
- Simplify: fewer data points, larger touch targets
- Rotate axis labels or use horizontal bar charts
- Reduce tooltip size
- Consider switching from multi-series to single-series with toggle
- Make charts touchable (pinch to zoom, tap for details)

### Container
- Use responsive SVG or Canvas
- Maintain aspect ratio (16:9 or 2:1 for most charts)
- Set min-height to prevent collapse
- Redraw on resize (debounced)

## Accessibility

### Data Tables
- Provide a data table alternative for screen readers
- Use `aria-label` to describe the chart
- Include a text summary of key findings

### Color
- Don't rely on color alone (add patterns or labels)
- Use colorblind-safe palettes
- Provide high contrast between data and background

### Animation
- Respect `prefers-reduced-motion`
- Don't animate continuously (distracting)
- One-time draw-in animation is fine

## Dashboard Layout

### Principles
- **Top-left:** Most important metric (KPI cards)
- **Top-right:** Secondary metrics
- **Middle:** Main chart(s)
- **Bottom:** Detail tables, secondary charts
- **Filters:** Top of dashboard, sticky

### KPI Cards
```
┌──────────┐ ┌──────────┐ ┌──────────┐
│ Revenue   │ │ Users    │ │ Churn    │
│ $48,250   │ │ 12,450   │ │ 2.3%     │
│ ↑ 12%     │ │ ↑ 8%     │ │ ↓ 0.5%   │
└──────────┘ └──────────┘ └──────────┘
```
- Big number, clear label
- Trend indicator (↑↓) with percentage
- Color: green for positive, red for negative
- Optional: sparkline showing trend

## Common Mistakes

| Mistake | Fix |
|---|---|
| 3D pie charts | Use 2D, always |
| Too many colors | Use 1 accent + grays |
| No axis labels | Always label axes |
| Tiny text | Min 12px for labels, 14px for values |
| No tooltip | Add interactive tooltips |
| Rainbow colormap | Use sequential or diverging palette |
| Dual y-axes | Avoid unless necessary; clearly label |
| No sorting | Sort bars by value |
| Truncated y-axis | Start at zero for bar charts |
| No legend or labels | Always identify your data |
