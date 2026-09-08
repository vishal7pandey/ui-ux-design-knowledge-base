# Undo and Destructive Actions

Undo and destructive-action patterns protect users from mistakes and give them confidence to act. When users know they can recover, they are more willing to use the product.

---

## 1. Destructive Actions

A destructive action removes, changes, or exposes something that is hard or impossible to reverse.

Examples:

- Delete a file, account, or project.
- Remove a team member.
- Change a public setting.
- Send a message or transfer money.
- Publish or post content.

---

## 2. Confirmation Patterns

### Simple confirmation dialog

For moderately destructive actions.

- State the consequence clearly.
- Use action-specific button labels: “Delete project” not “OK.”
- Provide a cancel option.

### Typed confirmation

For very destructive or irreversible actions.

- Ask the user to type a keyword (e.g., project name or “delete”).
- Use sparingly; it adds friction.

### Checkbox confirmation

For actions with multiple consequences.

- “I understand this will delete all associated data.”
- Prevent the action until checked.

---

## 3. Undo Patterns

### Toast with undo

- The action happens immediately.
- A toast appears with an “Undo” action.
- Undo is available for a limited time (5–10 seconds).

### Inline undo

- Allow users to undo directly in the context.
- Example: undo a change in a list or document.

### Revision history

- For complex work, keep a history of changes.
- Users can revert to a previous state.
- Common in documents, designs, and spreadsheets.

### Trash / recycle bin

- Deleted items go to a recoverable area.
- Users can restore before permanent deletion.
- Good for files, emails, and content.

---

## 4. When to Require Confirmation

| Action | Recommended pattern |
|--------|---------------------|
| **Send email / message** | No dialog; offer undo. |
| **Delete a file** | Confirmation dialog or trash pattern. |
| **Remove a user** | Confirmation dialog. |
| **Delete an account** | Typed confirmation. |
| **Publish public content** | Preview + confirmation. |
| **Transfer money** | Multi-step confirmation. |

---

## 5. Best Practices

- Reserve confirmations for real consequences.
- Use action-specific labels on confirmation buttons.
- Make cancel the safest, most obvious option.
- Provide an undo whenever possible.
- Preserve data until the undo window closes or the user explicitly completes the action.
- Be clear about what is recoverable and what is not.
- Match the friction to the stakes.

---

## 6. Time-Limited Undo

- Common for send, archive, delete.
- Show a progress bar or countdown.
- Allow users to dismiss the undo notice.
- Keep the action in a pending state until the window closes.

---

## 7. Confirmation Copy

- Be specific: “Delete ‘Q4 Report.pdf’ and remove it from all shared folders?”
- Explain consequences: “This cannot be undone.”
- Avoid vague questions: “Are you sure?”
- Use labels that state the action: “Delete,” “Remove,” “Transfer.”

---

## 8. Accessibility

- Ensure dialog is keyboard accessible.
- Move focus to the dialog on open.
- Return focus to the trigger on close.
- Provide clear labels and roles.
- Announce undo availability to screen readers.

---

## 9. Common Mistakes

- Confirming every small action.
- Using vague “Are you sure?” dialogs.
- Not providing undo.
- Making “Yes” or “Confirm” the default for destructive actions.
- Hiding the undo option.
- Losing data when the user cancels.
- Not matching the friction to the risk.

---

## 10. Checklist

- [ ] Destructive actions are identified and classified by severity.
- [ ] Confirmations match the stakes of the action.
- [ ] Buttons use action-specific labels.
- [ ] Cancel is the safest, most visible option.
- [ ] Undo is offered where possible.
- [ ] Time-limited undo is visible and accessible.
- [ ] Permanent deletion requires stronger confirmation.
- [ ] Users understand what cannot be undone.
- [ ] Dialogs are keyboard and screen-reader accessible.
- [ ] Data is preserved until the action is final.
