# AI Copilots and Sidekick Patterns

AI copilots are assistants that work alongside the user in the same context. They are not a separate chat; they are embedded in the task the user is already doing.

---

## 1. What Is a Copilot?

A copilot is an AI that:

- Is aware of the current task and context.
- Suggests, assists, or automates within the workspace.
- Is available but not intrusive.
- Helps the user do their work faster and better.

Examples: GitHub Copilot, Microsoft Copilot, Figma AI, Notion AI.

---

## 2. Copilot UX Principles

### Context-aware

The copilot knows what the user is doing.

- Current document, file, or screen.
- Recent actions and selections.
- User’s role and history.

### Available, not pushy

- Easy to invoke when needed.
- Suggestions appear when helpful, not constant.
- Can be minimized or hidden.

### Augment, not replace

- The user remains in control.
- The copilot accelerates, does not take over.
- Suggestions are easy to accept, edit, or reject.

### Fast and predictable

- Responses are quick.
- Suggestions are relevant to the moment.
- The copilot does not interrupt deep work.

---

## 3. Copilot Patterns

### Inline suggestions

- Suggest text, code, or values as the user types.
- Accept with Tab or click.
- Reject with Esc or by continuing to type.

### Side panel

- A persistent or toggleable panel beside the main workspace.
- Shows suggestions, chat, or tools.
- Good for writing, design, and analysis.

### Command palette

- User triggers the copilot with a shortcut.
- Type a command, get a result.
- Good for quick, specific actions.

### Selection-based actions

- User selects something and the copilot offers actions.
- “Summarize this,” “Rewrite this,” “Explain this.”
- Contextual to the selected content.

### Contextual chips

- Small suggestion chips appear based on the current state.
- Example: “Generate summary,” “Fix grammar,” “Add tests.”

### @-mentions

- User can @ the copilot in a document or chat.
- Brings the copilot into the current context.

---

## 4. Sidekick Patterns

A sidekick is a lighter, more ambient form of copilot.

- Watches the user’s work.
- Offers help when it detects a need or opportunity.
- Does not require explicit invocation.

### Examples

- “It looks like you’re writing a design spec. Want a template?”
- “You’ve been working on this task for an hour. Want a break reminder?”

### When to use

- The system can reliably detect the user’s intent.
- The suggestion is clearly helpful.
- The user can easily dismiss it.

---

## 5. Best Practices

- Make the copilot easy to find and invoke.
- Show suggestions that are relevant to the current moment.
- Let users accept, edit, or reject with one action.
- Do not interrupt the user’s flow.
- Provide a way to turn off or adjust suggestions.
- Keep the copilot’s personality consistent and helpful.
- Use the user’s language and context.
- Provide attribution for generated content.

---

## 6. Common Mistakes

- Suggestions that are irrelevant or distracting.
- Copilot takes over without permission.
- No way to accept, edit, or reject.
- Constant interruptions.
- Suggestions that do not fit the user’s context.
- Copilot that feels like a separate app, not part of the workflow.
- No way to disable or adjust the copilot.

---

## 7. Checklist

- [ ] Copilot is aware of the user’s current context.
- [ ] Invocation is easy and predictable.
- [ ] Suggestions are relevant and timely.
- [ ] Users can accept, edit, or reject suggestions.
- [ ] Copilot does not interrupt deep work.
- [ ] Users can adjust or disable the copilot.
- [ ] Generated content is attributed and editable.
- [ ] Copilot feels like part of the workspace, not a separate tool.
- [ ] Tone and personality are consistent.
- [ ] Sidekick suggestions are high-value and easy to dismiss.
