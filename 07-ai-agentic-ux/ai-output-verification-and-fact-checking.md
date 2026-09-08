# AI Output Verification and Fact-Checking

AI can produce plausible but incorrect output. Verification and fact-checking patterns help users trust what the AI gives them and catch errors before they matter.

---

## 1. Why Verification Matters

- AI models can hallucinate.
- Users may rely on AI for important decisions.
- Trust depends on the ability to check and confirm.
- High-stakes domains require evidence.

---

## 2. Verification Patterns

### Source citations

- Link each claim to a source document, page, or data point.
- Show the relevant excerpt.
- Allow users to open the original.

### Confidence scores

- Indicate how certain the AI is.
- Use labels: high, medium, low confidence.
- Explain the basis for the score.

### Evidence panels

- Show the raw data or reasoning behind the output.
- Let users expand to inspect.

### Fact check badges

- Mark content as verified, unverified, or partially verified.
- Use color and icon with text.

### Compare and contrast

- Show multiple sources or viewpoints.
- Help users see where information agrees or conflicts.

### Self-correction loops

- Let users flag incorrect output.
- Use the correction to update the model or response.

---

## 3. UI Patterns

### Highlighted sources

- Key claims are linked to source snippets.
- Hover or click reveals the reference.

### “Verify this” action

- User can request a fact-check on a specific statement.
- AI returns supporting or contradicting evidence.

### Source list

- A panel or appendix lists all sources used.
- Users can see when and where the AI got its information.

### Contradiction alerts

- If sources disagree, the UI shows the conflict.
- Users can decide which to trust.

### Timestamps and version

- Show when the source was last updated.
- Indicate the model version used.

---

## 4. High-Stakes Verification

For high-stakes output:

- Require human review before action.
- Show all sources and reasoning.
- Use multiple independent sources.
- Require explicit confirmation.
- Log the decision and evidence.

---

## 5. Best Practices

- Always provide sources where possible.
- Be honest about what is verified and what is not.
- Show uncertainty, not overconfidence.
- Make it easy to spot unverified claims.
- Let users challenge and correct output.
- Keep source links fresh and accessible.
- Use multiple sources for contentious claims.
- Update verification status as information changes.

---

## 6. Common Mistakes

- No source links.
- Vague confidence without explanation.
- Treating AI output as fact by default.
- Hiding or downplaying uncertainty.
- Not letting users report errors.
- Outdated or broken source links.
- No version or date on information.
- Over-automating verification in critical domains.

---

## 7. Checklist

- [ ] Sources are provided for claims.
- [ ] Confidence or uncertainty is communicated.
- [ ] Users can inspect evidence.
- [ ] Contradictions are shown.
- [ ] Unverified content is clearly marked.
- [ ] Users can request fact-checks.
- [ ] Users can report incorrect output.
- [ ] High-stakes output requires human review.
- [ ] Sources are dated and versioned.
- [ ] Verification status updates as information changes.
