# Error Handling and Recovery

Errors happen. Good error handling turns frustration into confidence by helping users understand, recover, and continue.

---

## 1. Error Types

| Type | Example | User need |
|------|---------|-----------|
| **User error** | Typo in a form. | Clear guidance to fix it. |
| **System error** | Server down. | Reassurance and a path forward. |
| **Network error** | Connection lost. | Know what is happening and how to retry. |
| **Permission error** | Access denied. | Understand why and what to do. |
| **Timeout** | Operation took too long. | Options to retry, cancel, or wait. |
| **Data error** | Missing or corrupt data. | Understand impact and recover. |

---

## 2. Error Message Structure

Every error message should answer:

1. **What happened.**
2. **Why it happened** (if helpful).
3. **What to do next.**

### Example

**Weak**: “Error 500.”
**Better**: “We couldn’t save your changes. The connection dropped. Your draft is safe. Try saving again.”

---

## 3. Error Display Patterns

### Inline errors

- Show next to the relevant field or action.
- Use for form validation and field-level problems.
- Link with `aria-describedby`.

### Inline alerts

- Show within a section or card.
- Use for localized problems that do not block the whole page.

### Banners

- Show at the top of a page.
- Use for persistent, important issues.

### Modals

- Block the user for critical, irreversible, or security issues.

### Toasts

- Use for transient, non-critical feedback.
- Do not use for errors that require user action.

---

## 4. Tone

Match the tone to the severity and the user’s emotional state.

| Severity | Tone |
|----------|------|
| **Light / easy to fix** | Neutral, instructive. |
| **User action failed** | Helpful, solution-focused. |
| **System error** | Apologetic, reassuring. |
| **Severe / data at risk** | Calm, clear, urgent. |

---

## 5. Recovery Paths

- **Retry**: try the action again, possibly with a delay.
- **Undo**: let the user reverse an action.
- **Fallback**: provide an alternative way to proceed.
- **Save state**: preserve user input and progress.
- **Help**: link to support, documentation, or next steps.

---

## 6. Prevention

- Validate early with inline feedback.
- Use defaults and constraints to reduce mistakes.
- Confirm destructive actions.
- Provide clear labels and helper text.
- Use progress indicators for long operations.

---

## 7. Network and Offline Errors

- Detect connection state and communicate it.
- Save user input locally where possible.
- Queue actions for retry when the connection returns.
- Show what is cached vs. live.
- Provide offline mode for critical tasks.

---

## 8. Accessibility

- Announce errors with `aria-live` regions.
- Pair color with icons and text.
- Ensure focus management for blocking errors.
- Provide clear keyboard paths to recovery.
- Do not rely on color alone.

---

## 9. Common Mistakes

- Generic messages like “Something went wrong.”
- Error codes without explanation.
- Blaming the user.
- Auto-dismissing critical errors.
- Losing user input on error.
- No recovery path.
- Inconsistent error tone or placement.
- Hiding errors in logs instead of the UI.

---

## 10. Checklist

- [ ] Every error explains what, why, and what to do.
- [ ] Error display matches the severity and scope.
- [ ] Inline errors are placed next to the relevant field.
- [ ] Critical errors do not auto-dismiss.
- [ ] User input and progress are preserved.
- [ ] Retry, undo, and fallback paths are provided.
- [ ] Tone matches the emotional impact.
- [ ] Network and offline states are handled.
- [ ] Errors are announced to screen readers.
- [ ] Errors are tested across devices and contexts.
