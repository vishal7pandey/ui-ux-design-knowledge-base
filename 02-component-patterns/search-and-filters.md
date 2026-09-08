# Search and Filters

Search and filtering are how users find what they need in large datasets. Good search UX reduces effort, while good filtering helps users narrow results without typing.

---

## 1. Search Patterns

### Simple search

A single input field with a search button or auto-submit.

**Best for**: small catalogs, straightforward queries.

### Suggested search

- Show autocomplete suggestions as the user types.
- Include recent, trending, and relevant suggestions.
- Use keyboard navigation for suggestions.

### Scoped search

- Let users search within a category or section.
- Use a dropdown or segmented control next to the search.

### Advanced search

- Provide filters, operators, and options for power users.
- Hide advanced options behind a toggle.

---

## 2. Search Input Design

- Place the search bar in a predictable location (top center or top right).
- Use a magnifying glass icon.
- Show placeholder text with a helpful example.
- Support autofocus on search-dense pages.
- Provide a clear way to clear the query.

---

## 3. Search Results

### Empty results

- Acknowledge the query.
- Suggest corrections, synonyms, or broader terms.
- Offer actions: clear filters, browse categories, contact support.

### Result cards

- Show the most relevant information first.
- Highlight matching terms.
- Use consistent formatting.
- Include images, ratings, and metadata when relevant.

### Loading

- Show a skeleton or spinner for async search.
- Debounce fast-typing queries.

---

## 4. Filter Patterns

### Faceted filters

- Side panel or top bar with multiple filter categories.
- Each selection narrows the result set.
- Show the number of results for each option.

### Filter chips

- Selected filters appear as removable chips.
- Help users see and manage active filters.

### Quick filters

- One-tap filters for common use cases.
- Example: “In stock,” “On sale,” “Top rated.”

### Sort

- Separate from filters but often combined.
- Provide the most useful sort options.
- Persist user choice.

---

## 5. Filter UX Best Practices

- Show filters where users expect them (top or side).
- Make active filters visible and removable.
- Allow users to reset all filters.
- Update results without full page reloads.
- Make filter labels match user language, not system language.
- Avoid overwhelming users with too many filters.
- Use progressive disclosure for advanced filters.

---

## 6. Autocomplete and Suggestions

- Show after 2–3 characters.
- Include categories, history, and trending.
- Allow arrow-key navigation and Enter selection.
- Avoid overly long suggestion lists.

---

## 7. Accessibility

- Label the search input.
- Announce result updates to screen readers.
- Make filter controls keyboard operable.
- Provide clear focus states.
- Do not rely on color alone for selected state.

---

## 8. Common Mistakes

- Search that requires exact matches.
- No results page with no guidance.
- Hidden or hard-to-find filters.
- Filters that do not show the effect immediately.
- Too many filters on a simple page.
- No way to clear or see active filters.
- Slow or unresponsive search results.

---

## 9. Checklist

- [ ] Search is easy to find and use.
- [ ] Autocomplete helps users refine queries.
- [ ] Results load quickly and are relevant.
- [ ] Empty results offer next steps.
- [ ] Filters are visible and easy to manage.
- [ ] Active filters are shown as removable chips.
- [ ] Sort and filter are easy to distinguish.
- [ ] Keyboard and screen-reader users can search and filter.
- [ ] Mobile search and filters are thumb-friendly.
- [ ] Search performance is tested with real data.
