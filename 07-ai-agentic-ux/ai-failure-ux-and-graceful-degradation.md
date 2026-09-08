# AI Failure UX and Graceful Degradation

AI will fail. How the product responds to those failures shapes trust and usability. Graceful degradation keeps the product useful even when the AI is unavailable, slow, or wrong.

---

## 1. Types of AI Failure

| Failure | Example | UX Response |
|---------|---------|-------------|
| **Latency** | Model takes too long to respond. | Show progress, offer retry, allow cancel. |
| **Timeout** | Model does not respond. | Explain and let the user retry or continue manually. |
| **Error** | API error or model outage. | Clear message, fallback path, manual alternative. |
| **Hallucination** | Model makes something up. | Confidence score, verification, source links. |
| **Inappropriate output** | Offensive, biased, or unsafe. | Filter, block, and report. |
| **Low confidence** | Model is unsure. | Ask the user, show alternatives, or decline. |
| **Context loss** | Model forgets the conversation. | Save and restore context, or re-prompt. |

---

## 2. Graceful Degradation

Graceful degradation means the product still works when AI is unavailable or limited.

### Strategies

- **Fallback to manual mode**: let the user do the task themselves.
- **Simplified output**: show a shorter or less polished result.
- **Cached results**: use previous or default responses.
- **Retry with backoff**: automatically retry after a delay.
- **Queue for later**: save the request and complete it in the background.

---

## 3. UX Patterns for AI Failure

### Loading and waiting

- Show a progress indicator.
- Provide an estimated time.
- Allow cancel.

### Retry

- Make retry obvious and easy.
- Explain what happened and why it may work on retry.
- Avoid endless auto-retry loops.

### Manual fallback

- Always have a way to complete the task without AI.
- For example, a search bar, form, or template.

### Partial results

- Show what the AI could do.
- Indicate what is missing or uncertain.
- Let the user continue with the partial result.

### Apologetic, informative messages

- Explain what happened.
- Reassure the user about their data.
- Provide a clear next step.

---

## 4. Hallucination Handling

- Show confidence or uncertainty.
- Provide sources and let users verify.
- Mark generated content as draft or speculative.
- For high-stakes content, require human review.
- Provide an easy way to report false information.

---

## 5. Over-Reliance Prevention

- Do not make AI the only way to complete a task.
- Encourage verification for important information.
- Show AI-generated content as a starting point, not a final answer.
- Let users edit and override.

---

## 6. Best Practices

- Design for failure from the start.
- Test common failure modes.
- Keep manual paths available.
- Be honest about what failed and why.
- Preserve user data and progress on failure.
- Use progressive disclosure to show technical details only when asked.
- Learn from failures and improve.

---

## 7. Common Mistakes

- Pretending the AI is not failing.
- No manual fallback.
- Blank or unhelpful error states.
- Blaming the user for the failure.
- Inconsistent error messages.
- Losing user input on failure.
- Over-relying on the AI for critical tasks.
- Not testing for failures.

---

## 8. Checklist

- [ ] Common failure modes are identified.
- [ ] Fallback paths exist for all AI features.
- [ ] Users can retry, cancel, or continue manually.
- [ ] Progress and status are shown during delays.
- [ ] Hallucinations are flagged and verifiable.
- [ ] User data is preserved on failure.
- [ ] Error messages are clear and helpful.
- [ ] Manual alternatives are always available.
- [ ] High-stakes AI output requires human review.
- [ ] Failures are logged and used to improve.
