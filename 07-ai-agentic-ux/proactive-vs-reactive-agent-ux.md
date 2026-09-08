# Proactive vs. Reactive Agent UX

Agents can either wait for user input (reactive) or act on their own (proactive). Each mode has different UX implications for trust, attention, and control.

---

## 1. Reactive Agents

A reactive agent responds only when the user explicitly asks.

### Examples

- A chatbot the user opens and messages.
- A command palette that runs a query.
- An AI that summarizes a document on request.

### When to use

- Users want control over timing.
- Tasks are complex or exploratory.
- The user needs to provide context.
- Trust is not yet established.

### UX patterns

- Input field, prompt, or command.
- Response in the same channel.
- Ability to refine, follow up, and start over.

### Strengths

- User is in control.
- Predictable and easy to understand.
- Lower risk of unwanted interruptions.

### Weaknesses

- User must know what to ask.
- Can feel slower.
- Requires more user effort.

---

## 2. Proactive Agents

A proactive agent takes action based on context, triggers, or predictions.

### Examples

- A reminder to follow up on an email.
- A suggestion to schedule a meeting based on availability.
- A notification that a report is ready.
- An alert that a metric is off track.

### When to use

- The product has enough context to anticipate needs.
- The action is clearly valuable and non-intrusive.
- The user has granted permission.
- The system is reliable and well-tested.

### UX patterns

- Suggestion chips.
- In-app notifications.
- Background task completion alerts.
- Contextual action prompts.

### Strengths

- Saves user effort.
- Helps users before they think to ask.
- Can increase engagement and value.

### Weaknesses

- Risk of being annoying or creepy.
- Requires strong privacy controls.
- Can erode trust if wrong.

---

## 3. Choosing Proactive vs. Reactive

| Factor | Reactive | Proactive |
|--------|----------|-----------|
| **User trust** | Lower trust needed. | Higher trust needed. |
| **Context** | User provides context. | System has context. |
| **Timing** | On demand. | Anticipated. |
| **Risk** | Lower. | Higher. |
| **Effort** | More user effort. | Less user effort. |

---

## 4. Hybrid Approaches

Most products use both modes.

### Reactive first, proactive later

Start with reactive features. Once trust and accuracy are high, add proactive features.

### Proactive with easy opt-out

- Let users turn proactive features on or off.
- Let users adjust frequency and channels.

### Proactive suggestions, user approval

- Propose actions, do not execute them.
- User approves with one tap.

### Proactive in the background

- Agent works quietly and reports when done.
- User can inspect and override.

---

## 5. Proactive UX Best Practices

- Only act on high-confidence, high-value triggers.
- Make it easy to dismiss or ignore.
- Explain why the agent acted.
- Provide clear value in every proactive message.
- Respect quiet hours and do-not-disturb.
- Learn from user feedback (thumbs up, dismiss, ignore).
- Never hide the fact that the agent was proactive.

---

## 6. Reactive UX Best Practices

- Provide clear entry points.
- Show example prompts or commands.
- Keep response times fast.
- Make it easy to refine or restart.
- Provide a history of past interactions.
- Use familiar UI, not hidden gestures.

---

## 7. Common Mistakes

### Proactive

- Too many proactive interruptions.
- Acting without permission or context.
- Suggestions that are irrelevant or wrong.
- No way to turn off proactive features.
- Failing to explain why the agent acted.

### Reactive

- Buried or hard-to-find agent entry points.
- No guidance on what to ask.
- Slow or unhelpful responses.
- No way to continue a previous conversation.

---

## 8. Checklist

- [ ] Proactive actions are high-confidence and high-value.
- [ ] Users can opt in or out of proactive features.
- [ ] Proactive messages explain the reason and value.
- [ ] Dismissing proactive messages is easy.
- [ ] Reactive agent is easy to find and use.
- [ ] Example prompts guide reactive users.
- [ ] Proactive and reactive modes work well together.
- [ ] Privacy and frequency controls are clear.
- [ ] Proactive features earn trust before expanding.
- [ ] Feedback is collected and used to improve.
