# Tables and Data Grids

Tables and data grids are the backbone of data-heavy products. They must present dense information clearly, support sorting and filtering, and remain usable on any screen.

---

## 1. Table Anatomy

```
[ Header row    ]  ← sortable, resizable columns
[_______________]
[ Data row 1    ]  ← selectable, expandable
[ Data row 2    ]
[ Data row 3    ]
[_______________]
[ Pagination    ]  ← or infinite scroll
```

---

## 2. Column Design

- Keep columns focused and meaningful.
- Use clear, short headers.
- Align text left, numbers right, dates left.
- Provide a minimum and maximum width.
- Allow users to show, hide, and reorder columns.

---

## 3. Sorting

- Indicate sortable columns with an icon.
- Default sort should match the user’s goal.
- Support ascending and descending order.
- Multi-column sort for power users.
- Make sure sort order is accessible.

---

## 4. Filtering

- Provide column-level filters.
- Use a filter bar for global filters.
- Show active filters as removable chips.
- Combine with search for complex datasets.

---

## 5. Pagination vs. Infinite Scroll

| Pagination | Infinite Scroll |
|------------|-----------------|
| Better for known result sets. | Better for feeds and exploration. |
| Users know how many results there are. | Users can keep exploring. |
| Good for comparison and reference. | Bad if users need to return to a specific row. |

For data grids, pagination is usually better because users may need to find a specific row.

---

## 6. Row Actions

- Provide a primary action per row.
- Use an actions menu for secondary actions.
- Bulk actions for selected rows.
- Inline editing where appropriate.

---

## 7. Selection

- Use checkboxes for multi-selection.
- Show selected count and bulk actions.
- Support select-all and clear selection.
- Maintain selection when sorting or filtering.

---

## 8. Empty, Loading, and Error States

- **Empty**: show a message and a CTA.
- **Loading**: use skeleton rows that match the grid structure.
- **Error**: show a message with retry and preserve filter state.

---

## 9. Responsive Tables

- Horizontal scroll with sticky first column.
- Collapse to cards on mobile.
- Prioritize the most important columns.
- Allow users to choose visible columns.
- Use a bottom sheet for filters on mobile.

---

## 10. Accessibility

- Use `<table>`, `<th>`, `<tr>`, `<td>` semantics where possible.
- Provide scope attributes for headers.
- Make sort controls keyboard operable.
- Announce sort and filter changes.
- Ensure contrast for zebra striping and selected rows.

---

## 11. Common Mistakes

- Too many columns on small screens.
- Hidden sort or filter controls.
- No empty or loading states.
- Inconsistent alignment.
- No way to select or act on rows.
- Infinite scroll for reference data.
- Missing column widths causing layout shift.

---

## 12. Checklist

- [ ] Columns are clear, sortable, and resizable.
- [ ] Filtering and search are available.
- [ ] Pagination or scroll is appropriate for the data.
- [ ] Row actions are easy to find and use.
- [ ] Multi-selection and bulk actions work well.
- [ ] Empty, loading, and error states are designed.
- [ ] Tables are usable on mobile.
- [ ] Keyboard and screen-reader users can navigate.
- [ ] Data alignment follows conventions.
- [ ] Column customization is supported.
