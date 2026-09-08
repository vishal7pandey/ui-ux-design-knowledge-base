# Micro-interactions

Micro-interactions are the small, focused moments when the interface responds to a user or system event. Done well, they make a product feel responsive, trustworthy, and alive. Done poorly, they feel slow, decorative, or distracting.

---

## 1. Anatomy of a Micro-interaction

Every micro-interaction has four parts:

1. **Trigger**: What starts it (click, tap, hover, scroll, system event).
2. **Rules**: The logic that determines the response.
3. **Feedback**: What the user sees, hears, or feels.
4. **Loops and modes**: Whether it repeats or changes over time.

---

## 2. Why Micro-interactions Matter

- **Feedback**: confirm that an action registered.
- **Status**: communicate what the system is doing.
- **Transitions**: show spatial or state relationships.
- **Guidance**: direct attention without words.
- **Personality**: express brand character through motion.

---

## 3. Timing Guidelines

| Duration | Use for |
|----------|---------|
| **0–100ms** | Hover, focus, immediate state changes. |
| **100–300ms** | Button presses, toggles, small transitions. Sweet spot for most UI feedback. |
| **300–500ms** | Modals, panels, page transitions, larger state changes. |
| **500ms+** | Progress animations, onboarding moments, or when the animation itself is the message. |

**Rule of thumb**: most micro-interactions should complete in **100–300ms**. Longer than 400ms feels sluggish.

---

## 4. Easing

| Easing | Use case |
|--------|----------|
| `ease-out` | Elements entering the screen. Fast start, gentle stop. |
| `ease-in` | Elements leaving the screen. Gentle start, fast exit. |
| `ease-in-out` | Elements that change state but remain in place. |
| `linear` | Avoid for UI motion; it feels mechanical. |

---

## 5. Feedback by Event Significance

| Significance | Feedback level | Duration | Example |
|--------------|----------------|----------|---------|
| **Micro** (hover, focus) | Subtle visual change | Instant, continuous | Background lightens on hover |
| **Minor** (tap, toggle) | Clear visual change | 100–300ms | Toggle slides, color shifts |
| **Medium** (save, send) | Visual change + state label | 1–3s | “Saved” appears briefly |
| **Major** (purchase, delete) | Multi-signal confirmation | 3–5s, user-dismissable | Confirmation banner with undo |
| **Critical** (error, failure) | Prominent, persistent | Until acknowledged | Red banner with error and action |

> **Use the least amount of feedback that still communicates the message.** A hover does not need a sound. A successful save does not need a full-screen animation.

---

## 6. Common Micro-interaction Patterns

### 6.1 Button feedback

- **Press state**: slight scale reduction (`0.96–0.98`) or background darkening.
- **Loading**: replace text with a spinner; disable to prevent double submission.
- **Success/failure**: briefly show a checkmark or X before returning to default.

### 6.2 Toggle switch

- Smooth slide of the handle.
- Track color change from off to on.
- Optional haptic or audio confirmation for mobile.

### 6.3 Form validation

- Validate on **blur**, not on every keystroke.
- Show a green check or red error icon near the field.
- Subtle horizontal shake on invalid submission.

### 6.4 Loading indicators

| Type | When to use |
|------|-------------|
| **Indeterminate spinner** | Unknown duration, expected < 10s. |
| **Determinate progress bar** | Duration known or estimable. |
| **Skeleton screen** | Content layout known, data loading. |
| **Step indicator** | Multi-step process. |
| **Inline spinner** | Loading inside a specific component. |

### 6.5 Notifications and toasts

- Enter from the edge or corner.
- Auto-dismiss after a few seconds for success; require dismissal for errors.
- Include a close affordance and an action link when relevant.

### 6.6 Pull-to-refresh

- Visual resistance and release threshold.
- Clear spinner during refresh.
- Confirmation when complete.

### 6.7 Swipe actions

- Show the action as the item is dragged.
- Snap to completion or back to original position.
- Provide haptic feedback on completion.

---

## 7. Best Practices

1. **Purpose over decoration**. Every animation must communicate something. If you cannot articulate what it answers, remove it.
2. **Match scale to action**. A checkbox does not need confetti.
3. **Respect user preferences**. Honor `prefers-reduced-motion`.
4. **Keep timing consistent**. Use a small, fixed set of durations.
5. **Make animations interruptible**. If the user acts again, the previous animation should not block them.
6. **Avoid jarring motion**. Avoid large, fast movements or flashing effects.
7. **Test on real devices**. Performance and feel vary across hardware.

---

## 8. Accessibility

- Honor `prefers-reduced-motion` by disabling non-essential animations.
- Do not rely on animation alone to convey meaning; pair with color, icons, or text.
- Avoid auto-playing, looping animations that cannot be paused.
- Ensure focus indicators are visible during transitions.

---

## 9. Quick Checklist

- [ ] Every micro-interaction has a clear communicative purpose.
- [ ] Duration is 100–300ms for small interactions.
- [ ] Easing matches the direction (enter = ease-out, exit = ease-in).
- [ ] Loading states are shown for async actions.
- [ ] Success and failure are clearly distinct.
- [ ] Animations respect `prefers-reduced-motion`.
- [ ] Feedback is proportional to the event significance.
- [ ] Users are not blocked by animations they did not trigger.
