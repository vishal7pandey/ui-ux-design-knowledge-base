# AI Safety and Harmful Output Prevention

AI can produce harmful, illegal, or unsafe content. Safety UX is about preventing, detecting, and recovering from harmful output while respecting user needs.

---

## 1. Types of Harmful Output

| Category | Example |
|----------|---------|
| **Hate speech** | Content targeting groups with hostility. |
| **Harassment** | Insults, threats, or bullying. |
| **Misinformation** | False or misleading claims. |
| **Dangerous instructions** | Instructions for self-harm, violence, or illegal acts. |
| **Privacy violations** | Exposing personal or sensitive data. |
| **Sexual or graphic** | Explicit, non-consensual, or harmful sexual content. |
| **Bias and stereotypes** | Reinforcing unfair generalizations. |

---

## 2. Safety Layers

### Prevention

- Content filters on input and output.
- Prompt classifiers.
- Refusal for known harmful requests.
- System instructions that discourage unsafe output.

### Detection

- Real-time scanning of generated content.
- User reporting.
- Automated classifiers and moderation.

### Response

- Refuse harmful requests clearly.
- Remove or block harmful output.
- Provide a path to appeal or report.
- Log and review incidents.

### Recovery

- Let users report false positives.
- Allow benign rephrases.
- Provide human review.
- Learn and update the system.

---

## 3. Refusal UX

When the AI refuses a request:

- Be clear about why.
- Use neutral, non-judgmental language.
- Do not lecture the user.
- Offer related, safe alternatives when possible.
- Provide a way to report false positives.

Example:

```
I can’t help with that. I can help with safe alternatives like [X] or [Y].
```

---

## 4. Harmful Output Handling

If harmful output is generated:

- Block or remove it quickly.
- Show a content warning if it is borderline.
- Let users report it.
- Do not blame the user.
- Provide clear next steps.

---

## 5. Content Warnings

- Use warnings for sensitive or potentially upsetting content.
- Let users choose to proceed.
- Explain why the content is flagged.
- Avoid over-warning; it can lose meaning.

---

## 6. User Reporting

- Make reporting easy and safe.
- Provide categories: harmful, inaccurate, biased, unsafe.
- Thank users for reporting.
- Follow up if the report leads to action.

---

## 7. False Positives

- Allow users to appeal or report a false block.
- Provide a way to rephrase or explain the benign intent.
- Review and learn from false positives.
- Do not make the appeals process slow or hidden.

---

## 8. Best Practices

- Design safety into the product from the start.
- Be transparent about safety rules.
- Protect users without being overly restrictive.
- Provide human review for edge cases.
- Test with red team and adversarial users.
- Keep safety policies updated.
- Respect user autonomy where possible.

---

## 9. Common Mistakes

- Refusing too many benign requests.
- Not explaining refusals.
- Lecturing or shaming users.
- No way to report false positives.
- Inconsistent safety rules.
- Not acting on harmful output reports.
- Treating safety as a technical issue, not a UX one.

---

## 10. Checklist

- [ ] Harmful output categories are defined.
- [ ] Prevention, detection, response, and recovery are in place.
- [ ] Refusals are clear and neutral.
- [ ] Users can report harmful or incorrect output.
- [ ] False positives can be appealed.
- [ ] Content warnings are used for sensitive content.
- [ ] Safety rules are transparent.
- [ ] Red team and adversarial testing are conducted.
- [ ] Safety policies are reviewed and updated.
- [ ] Safety is treated as a UX and product responsibility.
