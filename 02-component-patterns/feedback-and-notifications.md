# Feedback and Notifications

Feedback tells users what is happening, what happened, and what to do next. Good feedback is timely, clear, and appropriately prominent. Bad feedback is either missing or overwhelming.

---

## 1. Feedback Tiers

Match the feedback mechanism to the user’s attention needs.

| Tier | Pattern | Use when |
|------|---------|----------|
| **Inline** | Field-level error, button state, success checkmark | Feedback is tied to a specific element the user just interacted with. |
| **Ambient** | Status bar, notification tray, activity panel | A non-blocking state that persists until resolved. |
| **Transient** | Toast, snackbar | A brief confirmation or status that does not require action. |
| **Blocking** | Modal, alert dialog | Critical information that demands the user’s attention. |

---

## 2. Inline Feedback

Use when the feedback is directly tied to the element the user interacted with.

### Examples

- Button press state.
- Form field error or success.
- Toggle switch state change.
- Inline validation message.

### Best practices

- Keep feedback next to the trigger.
- Use a light touch for small interactions.
- Combine color, icon, and text; do not rely on color alone.
- For forms, place the error below the input and link it with `aria-describedby`.

---

## 3. Toasts and Snackbars

Use for low-priority confirmations and non-blocking status updates.

### When to use

- Action completed successfully.
- Non-critical status update.
- Undo opportunity.
- Background task finished.

### Best practices

- Keep messages short: one line, under 12 words.
- Limit to one action per toast (often “Undo”).
- Auto-dismiss after 4–6 seconds for simple messages.
- Pause the timer on hover or focus.
- Do not block critical UI or cover primary actions.
- Use `aria-live="polite"` for screen-reader announcements.

### Timing

| Toast type | Duration |
|------------|----------|
| Simple status | 4 seconds |
| With action (e.g., Undo) | 6–10 seconds or until dismissed |
| Critical (should not auto-dismiss) | Persistent |

---

## 4. Banners and Alerts

Use for important, persistent, non-blocking messages.

### When to use

- System status (maintenance, outage).
- Account-level warnings.
- Important feature announcements.
- Critical errors that do not block the whole page.

### Severity levels

| Type | Use for | Color convention |
|------|---------|------------------|
| **Info** | Neutral information | Blue |
| **Success** | Completed action | Green |
| **Warning** | Potential issue | Yellow / orange |
| **Error** | Problem requiring attention | Red |

### Best practices

- Be specific about what happened and what to do.
- Include a clear close or action.
- Do not stack too many banners on the same screen.
- Use `role="alert"` or `role="status"` as appropriate.

---

## 5. Modals for Critical Feedback

Use when the message blocks progress or requires a decision.

### When to use

- Confirming irreversible actions.
- Warning about unsaved changes before navigating away.
- Critical system errors that block the workflow.
- Permission or authentication required.

### Best practices

- State the consequence clearly in the title and body.
- Use clear action labels: “Delete project” not “OK.”
- Provide a safe, obvious cancel option.
- Focus the modal when it opens; return focus when it closes.

---

## 6. Error Messages

Every error message should answer:

1. What happened.
2. Why (if helpful).
3. What to do next.

### Examples

| Weak | Better |
|------|--------|
| Error 500 | Something broke on our end. Your data is safe. Try again in a moment. |
| Invalid input | Enter a date in DD/MM/YYYY format. |
| Access denied | Only workspace admins can change billing. Ask your admin or request access. |

### Best practices

- Use plain language, not codes or jargon.
- Be specific, not vague.
- Avoid blaming the user.
- Place the message near the relevant context.
- Provide a recovery path.

---

## 7. Loading and Progress Feedback

- For actions under 100ms, no separate indicator is usually needed.
- For 100ms–1s, a brief state change or spinner may help.
- For 1s–10s, use skeleton screens or progress indicators.
- Over 10s, show determinate progress and explanatory status.

### Best practices

- Delay loading indicators by 100–200ms to avoid flashes for fast actions.
- For long tasks, show steps and estimated time.
- Use optimistic UI for high-confidence, reversible actions.
- Provide a way to cancel or pause where applicable.

---

## 8. Notification Fatigue

Too many notifications cause users to dismiss them without reading. Avoid this by:

- Sending only what requires attention.
- Grouping related notifications.
- Respecting do-not-disturb or quiet hours.
- Letting users control frequency and channels.
- Using progressive escalation rather than loud alerts for everything.

---

## 9. Accessibility

- Announce dynamic content with `aria-live` regions.
- Use appropriate roles: `alert` for critical, `status` for non-critical.
- Ensure toasts are keyboard dismissible.
- Do not rely on color alone for severity.
- Preserve focus management for blocking feedback.

---

## 10. Common Mistakes

- Using toasts for critical errors that require action.
- Auto-dismissing important feedback before users can read it.
- Stacking multiple toasts in the same area.
- Using generic error messages with no recovery path.
- Relying on color alone for severity.
- Showing loading spinners for actions that complete quickly.
- Sending too many non-essential notifications.

---

## 11. Checklist

- [ ] Feedback is placed near the relevant element or context.
- [ ] Urgency of the message matches the mechanism (inline, toast, banner, modal).
- [ ] Error messages say what happened, why, and how to fix it.
- [ ] Toasts are short, dismissible, and pause on hover.
- [ ] Banners are persistent for important, non-blocking messages.
- [ ] Modals are reserved for critical decisions and blocking errors.
- [ ] Loading states match the action duration.
- [ ] Notifications are not overwhelming.
- [ ] Severity is communicated by more than just color.
- [ ] Screen readers announce state changes appropriately.
