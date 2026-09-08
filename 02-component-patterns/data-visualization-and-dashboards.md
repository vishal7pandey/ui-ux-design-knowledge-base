# Data Visualization and Dashboards

Dashboards help users monitor, understand, and act on data. Good dashboard design is about clarity, hierarchy, and turning raw data into decisions.

---

## 1. Dashboard Design Principles

- **Start with the user’s decisions**, not the data available.
- **Prioritize simplicity** over decoration.
- **Show the right level of detail** for the audience.
- **Provide context** so numbers are meaningful.
- **Enable action** from insights.

---

## 2. Audience and Purpose

| Dashboard type | Audience | Update frequency | Data density |
|----------------|----------|------------------|--------------|
| **Strategic** | C-suite, executives | Weekly, monthly, quarterly | Low — few KPIs |
| **Operational** | Managers, team leads | Daily or real-time | Medium — trends and summaries |
| **Analytical** | Analysts, data teams | On demand | High — drill-downs and filters |

Design each dashboard around one primary user and their most important decisions.

---

## 3. Dashboard Layout Framework

### Top-down hierarchy

```
Top:    Global filters, date range, key actions
Upper:  3–6 primary KPI cards
Middle: 1–3 primary charts / trends
Bottom: Detailed tables and secondary data
```

### KPI cards

- One number, one label, one comparison.
- Use large type for the headline metric.
- Add context: vs. previous period, vs. target, status.
- Limit to 3–6 cards at the top.

### Charts

- **Line chart**: trends over time.
- **Bar chart**: comparisons across categories.
- **Stacked bar / area**: parts of a whole (use for 5+ parts).
- **Pie / donut**: parts of a whole with 2–4 segments.
- **Table**: granular, sortable records.
- **Metric card**: single headline number.

> Start with the question the chart answers, then choose the visualization.

---

## 4. Data-Ink Ratio

Minimize non-data ink: borders, gridlines, 3D effects, shadows, and decorations. Every pixel should serve understanding.

- Remove unnecessary chart junk.
- Use light gridlines only when they aid reading.
- Avoid 3D charts; they distort perception.
- Directly label data points when possible instead of using a legend.

---

## 5. Visual Hierarchy and Attention

- **Size**: the most important numbers should be largest.
- **Color**: reserve strong colors for alerts and exceptions.
- **Position**: place primary KPIs in the top-left or top-center.
- **Whitespace**: group related metrics; separate unrelated ones.
- **Scanning**: support F-pattern and Z-pattern reading.

### Use color sparingly

- Red / orange: critical alerts or negative trends.
- Yellow / amber: warnings.
- Blue / green: positive or stable states.
- Gray: neutral, background, or secondary data.

---

## 6. Providing Context

A number without context is meaningless. Always provide:

- **Comparison**: vs. previous period, vs. goal, vs. benchmark.
- **Trend**: up/down arrow, sparkline, percent change.
- **Time range**: “Last 30 days,” “This quarter,” “Year to date.”
- **Status**: good / warning / critical based on thresholds.

---

## 7. Real-Time Dashboards

Real-time data adds cognitive challenges. Help users by:

- **Delta indicators**: show what changed and by how much.
- **Trend sparklines**: compact history for each metric.
- **Pause / snapshot**: let users freeze the view to analyze.
- **Plain language alerts**: explain what requires action.
- **Progressive disclosure**: show high-level first, detail on demand.

---

## 8. Interactivity

- **Drill-down**: click a summary metric to see detail.
- **Filters and date ranges**: let users control the view.
- **Hover / tooltips**: reveal exact values and context.
- **Sort and search**: for tables and lists.
- **Export and share**: for reports and collaboration.

---

## 9. Accessibility

- Do not rely on color alone; use labels, patterns, or icons.
- Provide text alternatives for charts.
- Use sufficient contrast for text and data.
- Make tables keyboard navigable.
- Offer data tables as an alternative to complex charts.
- Announce real-time updates politely.

---

## 10. Common Dashboard Anti-Patterns

- Too many KPIs on one screen.
- Charts chosen for visual appeal, not the question.
- Missing time context or comparison.
- 3D effects, excessive color, or unnecessary decoration.
- Dashboards that are dead ends with no drill-down.
- Mobile dashboards that just shrink the desktop view.
- Real-time dashboards with no way to pause or understand changes.

---

## 11. Checklist

- [ ] Dashboard is designed for a specific user and decision.
- [ ] Top section shows 3–6 critical KPIs.
- [ ] Charts match the question they answer.
- [ ] Data has context: comparison, trend, time range, status.
- [ ] Visual hierarchy guides attention.
- [ ] Non-data ink is minimized.
- [ ] Drill-down and interaction are available.
- [ ] Color is not the only channel for meaning.
- [ ] Real-time updates are manageable, not overwhelming.
- [ ] Mobile layout is redesigned, not just shrunk.
