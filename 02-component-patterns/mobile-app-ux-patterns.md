# Mobile App UX Patterns

Mobile UX has its own constraints and opportunities. Small screens, touch input, varying contexts, and limited attention require focused, efficient design.

---

## 1. Mobile Design Principles

- **One task per screen.** Mobile users are easily distracted; keep each screen focused.
- **Thumb-friendly design.** Place primary actions within easy reach.
- **Minimize input.** Use defaults, autofill, and simple controls.
- **Respect context.** Users may be on the move, in bright sunlight, or in quiet places.
- **Design for interruption.** Users pause and resume frequently; preserve state.

---

## 2. Navigation Patterns

### Bottom tab bar

- 3–5 primary destinations.
- Always visible for quick switching.
- Use icons with labels where possible.

### Hamburger menu

- For secondary or less-frequent items.
- Use sparingly; low discoverability.

### Top navigation

- Tabs under the header for local sections.
- Back button for hierarchical navigation.

### Gesture navigation

- Swipe, pull-to-refresh, and edge gestures.
- Provide visual affordances; do not rely solely on gestures.

---

## 3. Input and Forms

- Use the correct on-screen keyboard (`email`, `number`, `tel`, `date`).
- Minimize typing; use pickers, toggles, and autofill.
- Show progress for multi-step forms.
- Validate on blur, not on every keystroke.
- Use large touch targets (at least 48×48dp).

---

## 4. Mobile-Specific Patterns

### Pull-to-refresh

- Standard for lists and feeds.
- Provide clear feedback when complete.

### Swipe actions

- Common for mail, lists, and cards.
- Show the action icon and text as the user swipes.
- Provide haptic feedback on completion.

### Infinite scroll

- Good for feeds, bad for goal-oriented searches.
- Use pagination when users need to find a specific item.

### Bottom sheets

- Use for secondary content, filters, and actions.
- Keep primary content visible behind the sheet.

### Modals and full-screen

- Use full-screen for focused tasks.
- Provide a clear close or back action.

---

## 5. Touch and Gesture

- **Tap targets**: at least 48×48dp.
- **Spacing**: leave room between interactive elements.
- **Feedback**: show press states immediately.
- **Gestures**: supplement, not replace, visible controls.
- **Haptics**: use subtle, meaningful feedback for important actions.

---

## 6. Performance

- Optimize images and assets.
- Lazy load content below the fold.
- Cache data for offline or slow networks.
- Minimize launch time.
- Show skeletons or spinners for loading states.

---

## 7. Mobile Best Practices

- Keep copy short; mobile users scan.
- Use large, legible type.
- Ensure contrast in sunlight and dark mode.
- Test on real devices, not just simulators.
- Respect `prefers-reduced-motion`.
- Support dark mode and dynamic type.

---

## 8. Common Mistakes

- Shrinking a desktop design for mobile.
- Too much content on one screen.
- Hidden navigation without a clear way back.
- Tiny touch targets and crowded controls.
- Excessive scrolling or typing.
- Ignoring offline or poor-network conditions.

---

## 9. Checklist

- [ ] Each screen has a single primary task.
- [ ] Navigation is thumb-friendly and visible.
- [ ] Inputs use the right keyboard and are minimized.
- [ ] Touch targets meet minimum size.
- [ ] Forms validate on blur, not on every keystroke.
- [ ] Loading and offline states are handled.
- [ ] Gestures are supported but not the only control.
- [ ] Dark mode and reduced motion are supported.
- [ ] App is tested on real devices.
- [ ] Performance is optimized for mobile networks.
