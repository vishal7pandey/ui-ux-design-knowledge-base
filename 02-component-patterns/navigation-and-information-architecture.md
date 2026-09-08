# Navigation and Information Architecture

Good navigation starts with good information architecture (IA). IA is the structure; navigation is the visible mechanism that lets users move through it.

---

## 1. Information Architecture First

Before choosing a navigation pattern, answer these questions:

1. What are the 4–6 primary destinations users need most?
2. How do those destinations logically group?
3. What is the hierarchy of content within each section?
4. How do users search, scan, and switch contexts?

If the IA is wrong, no amount of navigation UI will fix it.

---

## 2. Navigation Pattern Catalog

### 2.1 Horizontal top navigation

**Use when**: 3–6 primary sections, relatively flat IA, marketing or content sites.

**Pros**: familiar, clean, does not consume vertical space.
**Cons**: runs out of room fast; does not scale to many sections.

**Best for**: landing pages, e-commerce, blogs, public sites.

---

### 2.2 Sidebar navigation

**Use when**: 5–15 sections, deep hierarchy, dashboards, admin tools, SaaS.

**Pros**: persistent, scannable, scales to many items.
**Cons**: consumes horizontal space on desktop; needs mobile fallback.

**Best for**: admin panels, project tools, analytics, internal tools.

---

### 2.3 Bottom tab bar (mobile)

**Use when**: 3–5 primary mobile destinations.

**Pros**: thumb-friendly, always visible.
**Cons**: limited to a few items.

**Best for**: consumer and productivity mobile apps.

---

### 2.4 Hamburger menu

**Use when**: secondary or less-frequent navigation on mobile.

**Pros**: saves space.
**Cons**: low discoverability; hidden items get less use.

**Best for**: secondary sections, settings, overflow on mobile.

---

### 2.5 Mega menu

**Use when**: many peer-level destinations, e-commerce, large enterprise sites.

**Pros**: exposes many links at once.
**Cons**: overwhelming if not structured.

**Best for**: e-commerce categories, enterprise homepages.

---

### 2.6 Breadcrumbs

**Use when**: 3+ levels of hierarchy, users land deep from search.

**Pros**: orients users, provides one-click path back.
**Cons**: add visual weight; less useful on flat sites.

**Best for**: e-commerce, documentation, file systems, deep content.

**Best practices**:

- Place below global navigation.
- Use `>` or `/` separators.
- Make all items except current clickable.
- Mark current page with `aria-current="page"`.
- Keep labels concise.

---

### 2.7 Command palette

**Use when**: power users, many actions, keyboard-driven workflows.

**Pros**: fast access to any screen or action.
**Cons**: not a replacement for visible navigation.

**Best for**: developer tools, design tools, dashboards, Notion/Linear-style apps.

---

### 2.8 Tabs (local / secondary navigation)

**Use when**: switching views within a single feature or record.

**Pros**: clear, space-efficient.
**Cons**: not for primary app navigation.

**Best for**: settings, detail views, dashboards.

---

## 3. Choosing the Right Pattern

| Question | Decision |
|----------|----------|
| Under 5 top-level items? | Top nav |
| 5–15 top-level items? | Sidebar |
| Over 15 top-level items? | Reconsider your IA |
| Constant switching? | Persistent sidebar or tab bar |
| Mobile-first? | Bottom tab bar + hamburger |
| Power users? | Add command palette |
| Deep hierarchy? | Breadcrumbs + sidebar |

---

## 4. Navigation Best Practices

- **Label by user intent**, not internal feature names.
- **Keep hierarchies shallow**: aim for no more than 3 levels.
- **Show current location**: active state, page title, breadcrumbs.
- **Design mobile navigation separately**; do not just shrink desktop nav.
- **Keep behavior consistent** across the product.
- **Combine patterns intentionally**: sidebar for global, top bar for context, breadcrumbs for depth, command palette for power users.

---

## 5. Mobile Navigation

- Use a bottom tab bar for 3–5 primary destinations.
- Use a hamburger menu for secondary or less-frequent items.
- Avoid hamburger-only navigation for primary actions; users will not see them.
- Consider a combined approach: bottom bar for primary, hamburger for more.

---

## 6. Accessibility

- Use semantic landmarks: `<header>`, `<nav>`, `<main>`, `<aside>`, `<footer>`.
- Provide a skip link to main content.
- Use `aria-label` for multiple `<nav>` elements.
- Mark the current item with `aria-current`.
- Ensure all navigation is keyboard operable.
- Make touch targets at least 48×48dp.

---

## 7. Common Mistakes

- Too many top-level items (more than 7).
- Deep nesting (more than 3 levels).
- Using the same mobile and desktop navigation without adaptation.
- Hiding the only path to key features in a hamburger menu.
- Inconsistent labels or navigation behavior across screens.
- Breadcrumbs on shallow or single-level sites.
- Skipping current-location indicators.

---

## 8. Checklist

- [ ] IA is mapped before navigation is designed.
- [ ] 4–6 top-level categories are clear and user-centered.
- [ ] Navigation pattern matches the number of sections and depth.
- [ ] Current location is always visible.
- [ ] Mobile navigation is designed separately.
- [ ] Breadcrumbs are used for 3+ level hierarchy.
- [ ] Command palette is available for power users (if relevant).
- [ ] All navigation is keyboard accessible.
- [ ] Touch targets meet minimum sizes.
