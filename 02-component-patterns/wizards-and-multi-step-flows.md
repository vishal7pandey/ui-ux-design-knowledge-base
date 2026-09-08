# Wizards and Multi-Step Flows

Wizards guide users through a sequence of steps to complete a complex task. They reduce cognitive load by breaking one big decision into smaller, manageable pieces.

---

## 1. When to Use a Wizard

Use a wizard when:

- A task is complex and has many fields or decisions.
- Users need guidance to complete the task correctly.
- Steps have a logical order.
- Users benefit from seeing progress.

Avoid a wizard when:

- The task is simple and can be done on one screen.
- Users need to compare or jump between steps.
- The form is short.

---

## 2. Wizard Structure

```
[ Step 1 → Step 2 → Step 3 → Step 4 ]
[__________________________]
[ Form content for current step ]
[ Previous ]          [ Next / Finish ]
```

### Key elements

1. **Step indicator** — shows current step and total steps.
2. **Step label** — describes what each step covers.
3. **Content area** — the form or task for the step.
4. **Navigation** — previous, next, and finish buttons.
5. **Summary** — review before final submission.

---

## 3. Best Practices

- Keep the number of steps low: 3–7 is ideal.
- Group related fields in each step.
- Show clear step labels.
- Allow users to move back and review.
- Validate each step before allowing forward movement.
- Save progress so users can resume.
- Show a final review step before submission.
- Provide a clear confirmation after completion.

---

## 4. Step Indicators

| Type | Use case |
|------|----------|
| **Horizontal stepper** | Top of the page, good for desktop. |
| **Vertical stepper** | Side panel, good for many steps or narrow layouts. |
| **Progress bar** | Linear, good for simple flows. |
| **Dots** | Compact, good for mobile. |

---

## 5. Navigation

- **Previous**: always available after step 1.
- **Next**: validates current step and advances.
- **Finish / Submit**: on the final step, with a review summary.
- **Skip**: for optional steps, if applicable.
- **Save and exit**: for long or complex wizards.

---

## 6. Validation

- Validate each step before allowing the user to proceed.
- Show errors inline, next to the relevant fields.
- Do not lose data when the user goes back.
- On final submission, validate the whole form.

---

## 7. Mobile Wizards

- Use a vertical stepper or simple progress bar.
- Show one step at a time.
- Keep buttons within thumb reach.
- Allow users to review all steps before submit.

---

## 8. Common Mistakes

- Too many steps.
- No visible progress.
- Not allowing users to go back.
- Losing data on navigation.
- No final review step.
- No clear way to save and resume.
- Asking for sensitive information too early.
- Validation only at the end.

---

## 9. Checklist

- [ ] Wizard is needed for the complexity of the task.
- [ ] Steps are grouped logically and are 3–7 in total.
- [ ] Step indicator is visible and clear.
- [ ] Users can move forward and back.
- [ ] Each step is validated before proceeding.
- [ ] Data is saved and preserved across steps.
- [ ] Final step includes a review summary.
- [ ] Confirmation is shown on completion.
- [ ] Mobile experience is simple and focused.
- [ ] Users can save and resume if needed.
