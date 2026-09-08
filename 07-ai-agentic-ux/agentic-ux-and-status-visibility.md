# Agentic UX and Status Visibility

Agentic systems do work on the user’s behalf. Status visibility is how users know what the agent is doing, whether it is on track, and when they need to act.

---

## 1. Why Status Visibility Matters

- Users should never wonder if the agent is working or stuck.
- Status reduces anxiety and uncertainty.
- It helps users decide when to wait, intervene, or step away.
- It builds trust by being transparent about progress.

---

## 2. Status States

| State | Meaning |
|-------|---------|
| **Idle** | Waiting for user input. |
| **Planning** | Deciding what to do. |
| **Running** | Executing a task. |
| **Waiting** | Paused for user input or external event. |
| **Completed** | Finished successfully. |
| **Failed** | Stopped due to an error. |
| **Needs review** | Output ready for user approval. |

---

## 3. Status Components

### Progress bar

- Good for long, linear tasks.
- Show overall progress and current step.

### Spinner or pulsing indicator

- Good for short, indeterminate waits.
- Avoid for long tasks without a progress bar.

### Step list

- Show each step in the task.
- Mark steps as pending, active, or complete.

### Agent cards

- One card per agent or sub-task.
- Show status, name, and current action.

### Log or timeline

- A running feed of actions and events.
- Useful for complex or long-running tasks.

### ETA

- Estimated time remaining.
- Use when the duration is predictable.

---

## 4. What to Show

- The current goal.
- The current step or agent.
- How much is done and how much remains.
- What the agent is doing right now.
- What the user needs to do, if anything.
- Any errors or warnings.
- How to cancel, pause, or get help.

---

## 5. Status by Task Type

### Simple task

- Spinner + brief status text.
- “Saving your changes…”

### Multi-step task

- Step list + progress.
- “Step 2 of 5: Analyzing documents…”

### Long-running task

- Progress bar + ETA.
- “Estimated time: 2 minutes.”

### Multi-agent task

- Agent cards + log.
- “Researcher: complete. Writer: in progress. Reviewer: pending.”

---

## 6. Best Practices

- Show status immediately when the agent starts.
- Update status in real time.
- Use clear, plain language.
- Make important status highly visible.
- Do not show too much detail by default.
- Let users expand for more information.
- Provide a way to cancel or pause.
- Show final status and next steps.

---

## 7. Common Mistakes

- No status for long tasks.
- Vague status like “Loading…”
- Fake progress bars.
- Too many notifications.
- Hiding errors until the end.
- Not showing when the agent needs input.
- Overwhelming users with technical detail.

---

## 8. Checklist

- [ ] Status is shown as soon as the agent starts.
- [ ] Current state and step are clear.
- [ ] Progress is visible for multi-step tasks.
- [ ] Real-time updates are provided.
- [ ] Language is plain and specific.
- [ ] Errors and warnings are shown immediately.
- [ ] Users can expand for details.
- [ ] Users can cancel, pause, or get help.
- [ ] Final status and next steps are communicated.
- [ ] Status does not overwhelm or distract.
