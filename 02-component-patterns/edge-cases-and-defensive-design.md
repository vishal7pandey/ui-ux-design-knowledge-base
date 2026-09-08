# Edge Cases and Defensive Design

Defensive design is designing for when things do not go as planned. Edge cases are unusual but possible situations that can break an otherwise good interface.

---

## 1. What Is Defensive Design?

Defensive design anticipates problems and builds the product to handle them gracefully. It covers:

- Empty, loading, and error states.
- Missing or malformed data.
- User mistakes and unexpected input.
- System failures and slow networks.
- Extreme values and limits.

---

## 2. Common Edge Cases

### Content extremes

- Very long names, titles, or descriptions.
- Very short or missing content.
- Special characters, emojis, and numbers.
- Right-to-left (RTL) text.
- Non-Latin scripts.

### Data extremes

- Zero, one, and many items.
- Maximum and minimum values.
- Out-of-range values.
- Duplicate data.
- Large numbers and dates far in the future or past.

### User behavior

- Fast repeated clicks.
- Going back and forward.
- Refreshing during an action.
- Closing the app mid-task.
- Using the app offline.

### System conditions

- Slow or lost connection.
- Low battery or storage.
- Small or large screens.
- Older browsers or devices.
- Disabled JavaScript or blocked permissions.

---

## 3. Defensive Design Principles

### Never trust the happy path

Design for what can go wrong, not just what should go right.

### Validate early and often

- Client-side and server-side validation.
- Inline validation for forms.
- Clear, specific error messages.

### Plan for the worst

- What happens if the server is down?
- What happens if the user loses connection?
- What happens if a file is too large?

### Provide defaults

- Sensible defaults for empty or missing data.
- Graceful fallbacks for failed operations.

### Preserve user work

- Auto-save where possible.
- Restore state on error or reconnection.
- Allow users to recover from mistakes.

---

## 4. Patterns

### Empty states

- Show what the screen is for.
- Provide a clear next action.
- Use illustrations and copy that guide users.

### Loading states

- Match the loading duration.
- Skeletons for content, spinners for actions.
- Progress for long tasks.

### Error states

- Explain what happened, why, and how to fix it.
- Preserve input and state.
- Provide retry or fallback.

### Confirmations

- For destructive, high-stakes, or irreversible actions.
- Use specific labels and clear consequences.

### Input limits

- Min and max lengths.
- Character whitelists where needed.
- File size and type restrictions.
- Clear messaging when limits are hit.

---

## 5. Testing for Edge Cases

- Use real data, not just sample data.
- Test with the smallest and largest possible values.
- Test with slow networks and offline mode.
- Test on old devices and browsers.
- Test with assistive technology.
- Test with different languages and scripts.
- Try to break the product intentionally.

---

## 6. Common Mistakes

- Only testing with ideal data.
- Forgetting empty and error states.
- No fallback for failed operations.
- Blaming the user for errors.
- Losing user input on failure.
- Ignoring performance on slow devices.
- Not handling special characters or long text.
- No confirmation for destructive actions.

---

## 7. Checklist

- [ ] Empty, loading, and error states are designed.
- [ ] Forms validate on blur and submit.
- [ ] Error messages are specific and actionable.
- [ ] Long, short, and missing content are handled.
- [ ] Special characters and non-Latin scripts are supported.
- [ ] Large and small numbers are formatted.
- [ ] Slow and offline states are supported.
- [ ] User input is preserved on failure.
- [ ] Destructive actions are confirmed.
- [ ] Performance is tested on low-end devices.
- [ ] Accessibility is tested with assistive technology.
- [ ] The product is intentionally stress-tested.
