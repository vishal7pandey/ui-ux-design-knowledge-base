# Form Design and Validation

Forms are one of the most common and highest-friction parts of any product. Good form design reduces errors, increases completion rates, and builds trust.

---

## 1. Form Structure

### Anatomy of a field

```
[ Label                    ]  ← always visible
[ Helper text (optional)   ]  ← before the input
[__________________________]  ← input
[ Inline error message     ]  ← appears when invalid
```

### Best practices

- Keep labels visible and close to inputs.
- One column is usually better than multiple columns.
- Group related fields visually.
- Order fields to match the user’s mental model and task flow.
- Mark required fields explicitly. Or, if most are optional, mark optional fields instead.

---

## 2. Labels

- Every input needs a label. Placeholders are not labels.
- Labels should be clear and specific: “Work email” not “Email.”
- Use sentence case for labels.
- Keep labels visually above or beside the input; do not rely on placeholder text.

---

## 3. Helper Text

- Show constraints before the user types: “Password must be at least 8 characters.”
- Use helper text for formatting hints: “DD/MM/YYYY.”
- Keep it short. One line if possible.
- Do not repeat the label.

---

## 4. Inline Validation

### When to validate

1. **Do not validate while the user is typing.** No live red borders. The user is still forming their input.
2. **Validate on blur** (when focus leaves the field). The user has finished entering the field.
3. **Re-validate on subsequent keystrokes once an error is showing.** This lets the user see they fixed the issue immediately.
4. **Validate the whole form on submit** as a final check.

### Error message placement

- Place inline error text immediately below or beside the input.
- Link the message to the field with `aria-describedby`.
- Use `aria-invalid="true"` when a field is invalid.
- Do not rely only on color; add an icon or text cue.

### Error message content

- Name the specific problem.
- Explain how to fix it.
- Keep it short, friendly, and non-accusatory.

| Weak | Better |
|------|--------|
| Invalid input | Enter a date in DD/MM/YYYY format |
| Password error | Password must be at least 8 characters and include a number |
| Email invalid | Add the @ to your email address |

---

## 5. Submission and Error Summaries

For complex forms, also show an error summary at the top on submit:

- Lists all errors.
- Links directly to each invalid field.
- Receives focus so screen readers announce it.

```
<div tabindex="-1" role="alert" aria-live="assertive">
  <h2>There is a problem</h2>
  <ul>
    <li><a href="#email">Enter a valid email address</a></li>
    <li><a href="#password">Password must include a number</a></li>
  </ul>
</div>
```

---

## 6. Field Types and Inputs

### Text and email

- Use the correct `type` attribute (`email`, `tel`, `url`, `number`).
- Use `autocomplete` to help browsers autofill fields.
- For dates, use `<input type="date">` or a well-tested date picker.

### Passwords

- Show a toggle to reveal the password.
- Provide strength feedback as the user types.
- Allow paste in password fields. Do not block password managers.
- Do not require arbitrary rules; use minimum length as the primary constraint.

### Select and radio

- Use radio buttons for 5 or fewer mutually exclusive options.
- Use a select dropdown for 6–15 options.
- Use an autocomplete for more than 15 options.
- Avoid multi-select dropdowns; use checkboxes or a searchable list instead.

### Checkboxes and toggles

- Use a checkbox for independent, binary settings.
- Use a toggle switch for on/off settings that take effect immediately.
- Use a single checkbox for agreement, not a toggle.

---

## 7. Error Prevention

- Disable submit until required fields are filled.
- Use constraints and formatting to prevent mistakes.
- Confirm destructive or irreversible actions.
- Provide inline hints before the user makes an error.

---

## 8. Progress Indicators

For multi-step forms:

- Show the current step, total steps, and progress.
- Allow users to go back and review or edit previous steps.
- Save progress so users can resume if interrupted.
- Show a review step before final submission.

---

## 9. Accessibility

- Use semantic HTML (`label`, `input`, `fieldset`, `legend`, `button`).
- Associate labels with inputs using `for` and `id`.
- Use `aria-describedby` for helper text and errors.
- Ensure focus order is logical.
- Make focus indicators visible.
- Do not rely on color alone for error states.
- Allow full keyboard operation.
- Test with screen readers and high-contrast mode.

---

## 10. Mobile Form Considerations

- Use appropriate input types to trigger the right on-screen keyboard.
- Ensure tap targets are at least 48×48dp.
- Avoid dense multi-column layouts.
- Show the numeric keyboard for phone, zip, and card fields.
- Minimize typing with autocomplete, select, and date pickers.

---

## 11. Common Mistakes

| Mistake | Fix |
|---------|-----|
| Validating on every keystroke | Validate on blur and submit |
| Placeholders as labels | Always use visible labels |
| Vague errors like “Invalid” | Explain the specific problem and how to fix it |
| Red color only | Add icons and text cues |
| Inline error far from the field | Place it directly below the input |
| No error summary for long forms | Add a top-of-form summary on submit |
| Blocking paste in password fields | Allow paste and password managers |
| Multi-select dropdowns | Use checkboxes or searchable lists |
| Hidden required indicators | Mark required fields clearly |

---

## 12. Checklist

- [ ] Every field has a visible label.
- [ ] Helper text explains constraints before the user types.
- [ ] Required fields are clearly marked.
- [ ] Validation happens on blur and submit, not mid-typing.
- [ ] Error messages are specific and actionable.
- [ ] Errors are placed next to their fields and linked with `aria-describedby`.
- [ ] Error summary is available for complex forms.
- [ ] Submission button is disabled until the form is ready.
- [ ] Multi-step forms show progress and allow navigation.
- [ ] Form is fully keyboard accessible.
- [ ] Mobile inputs trigger the correct keyboard.
- [ ] Accessibility is tested with screen readers.
