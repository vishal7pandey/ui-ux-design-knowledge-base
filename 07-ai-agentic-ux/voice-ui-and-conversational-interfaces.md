# Voice UI and Conversational Interfaces

Voice interfaces let users interact with systems through spoken language. They are fast, hands-free, and natural, but they also introduce unique design challenges around latency, ambiguity, and feedback.

---

## 1. When to Use Voice

Voice is ideal for:

- Hands-free or eyes-free tasks.
- Quick queries and commands.
- Multitasking (driving, cooking, exercising).
- Users with motor or vision impairments.

Voice is poor for:

- Long or complex forms.
- Visual comparison tasks.
- Private information in public spaces.
- Noisy or quiet environments.

---

## 2. Core Voice UX Principles

### Conversation is turn-based

Users and the system take turns. Each turn should have a clear purpose and an obvious end.

### One breath test

A system response should be short enough to say in one breath. Long responses feel unnatural and are hard to remember.

### Repair gracefully

When the system does not understand, help the user recover without blame.

- “I didn’t catch that. Did you mean 7 PM or 8 PM?”
- “I can help with weather, timers, or news. Which one?”

### Confirm high-stakes actions

- “I’ll send $200 to Alex. Is that right?”
- Use explicit confirmation, not just “Okay, sending.”

### Provide feedback for latency

Listening, thinking, and responding all take time. Use sounds or visual cues to show the system is working.

---

## 3. Listening States

| State | User need | Feedback |
|-------|-----------|----------|
| **Idle** | Know when to speak. | Wake word prompt or visual indicator. |
| **Listening** | Know the system is hearing them. | Sound or animation. |
| **Processing** | Know the system is thinking. | Subtle sound or loading animation. |
| **Responding** | Know the system is speaking. | Audio output, visual transcript. |

---

## 4. Error Handling in Voice

- **No-match**: the system did not understand.
  - “Sorry, I didn’t get that. Try saying it another way.”
- **No-input**: the user did not say anything.
  - “I’m still here. What can I do for you?”
- **Ambiguity**: multiple interpretations.
  - “Did you mean Paris, France or Paris, Texas?”
- **Out of scope**: the user asked for something the system cannot do.
  - “I can set timers and reminders. I can’t make calls yet.”

---

## 5. Multimodal Voice Interfaces

Voice often works best with a screen.

- **Show a transcript** of what the system heard.
- **Display results** while speaking them.
- **Use cards** for lists, images, and structured info.
- **Allow touch fallback** for selection and correction.

---

## 6. Conversational Interface Patterns

### Greetings and exits

- Open with a clear, friendly offer.
- Make exit commands obvious.
- Provide help at any point.

### Slot filling

When multiple pieces of information are needed, ask one at a time.

```
User: “Book a table.”
System: “For how many people?”
User: “Four.”
System: “What time?”
```

### Disambiguation

When meaning is unclear, ask clarifying questions instead of guessing.

### Progressive clarification

Start broad, then narrow.

### Barge-in

Let users interrupt the system when they already know the answer.

---

## 7. Accessibility in Voice

- Provide text transcripts of spoken content.
- Allow keyboard or touch alternatives.
- Support visual impairments with clear audio cues.
- Support hearing impairments with on-screen text.
- Respect `prefers-reduced-motion` for visual listening indicators.

---

## 8. Common Mistakes

- Designing voice like a visual interface.
- Over-explaining in system responses.
- Not handling errors gracefully.
- No feedback during processing.
- Asking for too much information in one turn.
- Failing to confirm high-stakes actions.
- Ignoring multimodal opportunities.

---

## 9. Checklist

- [ ] Voice is the right medium for the task.
- [ ] Turns are short and purposeful.
- [ ] Listening states are clearly signaled.
- [ ] Errors are handled with repair and clarification.
- [ ] High-stakes actions are confirmed.
- [ ] Multimodal feedback is used when a screen is available.
- [ ] Barge-in is supported.
- [ ] Accessibility alternatives are provided.
- [ ] System responses pass the one-breath test.
- [ ] Users can get help and exit at any time.
