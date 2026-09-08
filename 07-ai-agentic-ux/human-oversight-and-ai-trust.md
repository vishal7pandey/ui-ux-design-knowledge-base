# Human Oversight and AI Trust

Trust in AI is not automatic. Users need control, transparency, and the ability to intervene. Human oversight is the design pattern that keeps humans in charge while AI handles the work.

---

## 1. Levels of Human Oversight

| Level | Name | When to use |
|-------|------|-------------|
| **HITL** | Human-in-the-Loop | The AI proposes, the human approves every action. |
| **HOTL** | Human-on-the-Loop | The AI acts, the human supervises and can intervene. |
| **HIL** | Human-in-Command | The human sets goals, the AI executes autonomously within bounds. |

### HITL

- User reviews every AI action before it happens.
- Best for high-stakes, irreversible, or regulated decisions.
- Higher friction, but higher trust.

### HOTL

- AI acts and the user monitors.
- User can pause, override, or stop.
- Best for workflows that need speed with guardrails.

### HIL

- User sets the strategy and constraints.
- AI operates within the boundaries.
- Best for mature, well-trusted agents.

---

## 2. Building Trust in AI

### Transparency

- Show what the AI is doing.
- Explain why it made a suggestion.
- Cite sources and data.
- Show confidence levels.

### Control

- Let users approve, edit, reject, and undo.
- Provide settings to adjust AI behavior.
- Allow users to disable AI features.

### Accountability

- Make it clear who is responsible for decisions.
- Log AI actions for review.
- Provide recourse when the AI is wrong.

### Competence

- The AI should perform reliably within its stated limits.
- Do not overpromise.
- Gracefully handle uncertainty and failure.

---

## 3. Oversight Patterns

### Approval queues

- AI gathers proposals.
- User reviews and approves in a list or queue.
- Useful for bulk actions, moderation, or content creation.

### Escalation chains

- Low-confidence or high-risk actions are escalated to a human.
- Define thresholds for escalation.
- Notify the right person with context.

### Watch mode

- AI runs in the background.
- User sees a live feed of actions.
- User can pause or override at any time.

### Shadow mode

- AI makes predictions but does not act.
- Human decisions are compared to AI recommendations.
- Useful for training and validation.

### Human override

- User can take over from the AI at any time.
- Provide a clear, easy-to-find override control.
- Preserve state when switching.

---

## 4. Trust Signals

- Consistent, reliable behavior.
- Clear capability statements.
- Honest uncertainty.
- Attribution for sources and reasoning.
- Fast recovery from errors.
- Respect for user time and attention.

---

## 5. Design for Failure

- The AI will be wrong sometimes.
- Make it easy to report and correct mistakes.
- Provide fallback paths to human support.
- Do not blame the user or the AI.
- Learn from corrections.

---

## 6. Best Practices

- Match the oversight level to the risk and confidence of the task.
- Set clear boundaries for autonomous action.
- Keep the user informed, not overwhelmed.
- Make approval and override easy.
- Design for graceful degradation.
- Provide clear attribution and logs.
- Respect user agency.

---

## 7. Common Mistakes

- No oversight for high-stakes actions.
- Too much oversight, slowing users down.
- Hiding AI actions from the user.
- No way to undo or correct AI mistakes.
- Over-promising AI capabilities.
- Failing to explain why the AI did something.
- Not providing recourse when the AI is wrong.

---

## 8. Checklist

- [ ] Oversight level matches the task risk.
- [ ] Users can approve, edit, reject, and undo AI actions.
- [ ] AI actions are visible and logged.
- [ ] Sources and reasoning are shown.
- [ ] Confidence and uncertainty are communicated.
- [ ] Escalation thresholds are defined.
- [ ] Users can override or disable AI at any time.
- [ ] Failures are easy to report and recover from.
- [ ] Responsibility for decisions is clear.
- [ ] Trust is built through reliable behavior and honest limits.
