# Empty States, Loading, and Onboarding

Transitional moments — loading, empty screens, and first-time setup — disproportionately affect how users perceive your product. These are not afterthoughts; they are opportunities to build trust and guide action.

---

## 1. Empty States

An empty state appears when a screen has no content: a new account, no search results, a completed list, a missing connection.

### Types of empty states

| Type | When it appears | What to show |
|------|-----------------|--------------|
| **First-time use** | New user, nothing created yet | What the feature does + primary CTA |
| **No results** | Search or filter returned nothing | Acknowledge the query + corrective action |
| **Cleared / completed** | User finished or deleted all items | Confirmation + path back to activity |
| **Unavailable** | No connection, permission denied, or failure | What went wrong + retry or support |

### Empty state structure

1. **Headline**: what is happening.
2. **Description**: why it is empty and why it matters.
3. **Illustration or icon**: sets the mood, not decoration.
4. **Primary action**: the single most useful next step.
5. **Secondary action** (optional): an alternative path.

### Examples

| Screen | Weak | Better |
|--------|------|--------|
| Inbox | No messages | No messages yet. Conversations with your team will show up here. Start a conversation. |
| Search | No results | No results for “prodct.” Did you mean “product”? Or browse by category. |
| Favorites | Empty | Your favorites will appear here. Save items for quick access. Browse items. |
| Projects | No projects | Projects you create or join will appear here. Create your first project. |

### Best practices

- Never show a blank screen.
- Make the first-use empty state a small onboarding moment.
- Distinguish empty from loading and error.
- Use one clear primary action.
- Match the illustration and tone to the feature.

---

## 2. Loading States

### Perceived performance

Actual speed matters, but perceived speed matters more. A well-designed loading state can make a wait feel shorter and less frustrating.

### Loading indicators by duration

| Duration | Best pattern |
|----------|--------------|
| **Under 300ms** | Usually no indicator needed. |
| **300ms – 1s** | Brief spinner or subtle state change. |
| **1s – 10s** | Skeleton screen for known layouts; spinner for unknown. |
| **Over 10s** | Determinate progress bar with status text or background processing. |

### Skeleton screens

Skeleton screens show the layout of upcoming content with placeholder shapes.

**When to use**:

- Layout is predictable.
- Content is coming in predictable quantity.
- You want to reduce layout shift and perceived wait time.

**Best practices**:

- Match the final layout closely.
- Use a subtle shimmer animation (1–1.5s cycle).
- Do not use fake readable text or clickable controls.
- Mark the region as `aria-busy="true"`.

### Spinners

**When to use**:

- Layout is unknown or unpredictable.
- Action is brief and localized (e.g., a button loading state).

**Best practices**:

- Give spinners an accessible name: “Loading your projects.”
- Do not show a spinner over a blank white screen.
- Do not let a spinner run forever without a timeout or error state.

### Optimistic UI

For high-confidence, reversible actions (like, toggle, send), update the UI immediately and sync in the background. Revert if the request fails.

---

## 3. Error States

When loading or an action fails, show a clear, actionable error state.

### Structure

1. What happened.
2. Why it happened (if known).
3. What the user can do next.

### Examples

| Weak | Better |
|------|--------|
| Something went wrong | Reports could not load. The connection dropped. Retry or use cached data. |
| No internet | No internet connection. Your data is safe. Try again when you’re back online. |

### Best practices

- Preserve user input and context.
- Offer a retry or alternative path.
- Do not use HTTP codes alone.
- Do not clear the user’s work on failure.

---

## 4. Onboarding

Onboarding is the process of helping new users become successful. It is not just a tour; it is a sequence of value-building moments.

### Onboarding principles

- **Show value, not features.** Users care about what they can do, not every capability.
- **Start with action.** Get the user to do something useful as soon as possible.
- **Minimize upfront setup.** Ask only what you need.
- **Make it skippable and resumable.** Do not force users through a wall.
- **Use empty states as tutorials.** Each empty screen is a chance to explain a feature.

### Common onboarding patterns

| Pattern | Use case |
|---------|----------|
| **Welcome screen** | Set expectations and prompt the first action. |
| **Progressive disclosure** | Reveal features as the user needs them. |
| **Contextual tooltips** | Highlight one action at a time during first use. |
| **Checklist** | Show a list of setup steps, e.g., “Complete your profile.” |
| **Sample data** | Pre-populate dashboards so the product feels alive. |
| **Wizard** | Guided multi-step setup for complex products. |

### Onboarding checklist

- [ ] First action is clear and quick.
- [ ] Users can skip and return later.
- [ ] Each step provides value or context.
- [ ] Setup is minimal; advanced options are deferred.
- [ ] Empty states explain the next action.
- [ ] Tooltips do not block essential UI.
- [ ] Users reach an “aha” moment within the first session.

---

## 5. Accessibility

- Announce loading states with `aria-live="polite"` or `aria-busy="true"`.
- Give loading indicators accessible names.
- Do not move focus to skeleton elements.
- Make sure error messages are announced.
- Empty states should be in the normal reading order.
- Onboarding tooltips should be keyboard dismissible.

---

## 6. Common Mistakes

- Showing a blank area during loading.
- Using the same empty state for loading, no-results, and errors.
- Skeleton that does not match the final layout.
- Spinners that run forever.
- Clearing user input on an error.
- Forcing users through a mandatory, long onboarding tour.
- Onboarding that explains features instead of value.
- Tooltips fired while targets are still loading.

---

## 7. Checklist

- [ ] Every empty screen has a headline, description, and action.
- [ ] First-use empty states are treated as onboarding.
- [ ] Loading and empty states are visually distinct.
- [ ] Skeletons match the final layout.
- [ ] Spinners have accessible names and timeouts.
- [ ] Errors explain what happened and how to recover.
- [ ] Onboarding is skippable, resumable, and action-oriented.
- [ ] Tooltips and tours trigger only after content is ready.
- [ ] All states are tested with assistive technology.
