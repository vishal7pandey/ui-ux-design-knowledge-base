# AI Transparency and Model Cards

Transparency is about showing how AI works, what it can do, and where it has limits. Model cards are one way to communicate this to users in a structured, accessible format.

---

## 1. Why AI Transparency Matters

- Users need to know what to expect.
- Stakeholders need to assess risk and suitability.
- Regulators and auditors need documentation.
- Trust grows when the system is honest about its limits.

---

## 2. What to Disclose

### Capabilities

- What the AI can do.
- What tasks it is trained or tuned for.
- The languages, formats, or domains it supports.

### Limitations

- What the AI cannot do.
- Known failure modes.
- Types of questions or data it handles poorly.
- Situations where it should not be used.

### Data and training

- What data the model was trained on.
- Whether user data is used for training.
- How data is processed and stored.

### Performance

- How accurate or reliable the model is.
- For which use cases it is evaluated.
- Known biases or gaps.

### Use cases

- Intended uses.
- Out-of-scope or risky uses.
- Recommendations for human oversight.

---

## 3. Model Cards

A model card is a standardized document that summarizes an AI model’s purpose, performance, and limitations.

### Typical sections

- **Model name and version**
- **Developer or organization**
- **Intended use cases**
- **Out-of-scope uses**
- **Input and output types**
- **Training data**
- **Evaluation metrics and results**
- **Ethical considerations and limitations**
- **Caveats and recommendations**

---

## 4. UX Surfaces for Transparency

### About this AI

- A panel or page with a concise summary of the AI.
- Capabilities, limitations, and data use.
- Link to the full model card or documentation.

### Confidence and uncertainty

- Show how certain the AI is about an answer.
- Flag when the answer is speculative or not found.

### Sources and attribution

- Link to the data or documents used.
- Show dates and provenance.

### Limitation notices

- In-context warnings for high-risk or low-confidence areas.
- Example: “I can make mistakes. Verify important information.”

### Changelog

- Track changes to the model or system.
- Explain how updates might affect outputs.

---

## 5. Best Practices

- Use plain language, not model or academic jargon.
- Be specific about limitations, not vague.
- Place key information where users need it.
- Link to more detail for those who want it.
- Update transparency materials as the model changes.
- Do not overstate capabilities.
- Be honest about uncertainty.

---

## 6. Common Mistakes

- Hiding that a feature uses AI.
- Vague or unhelpful disclaimers.
- No information about data use.
- Overstating accuracy or reliability.
- Model cards that are only for engineers.
- Not updating transparency as the model changes.
- Failing to flag known failure modes.

---

## 7. Checklist

- [ ] It is clear when and where AI is used.
- [ ] Capabilities and limitations are documented.
- [ ] Data use and training are explained.
- [ ] Performance and evaluation are shared.
- [ ] Model card or transparency page is accessible to users.
- [ ] In-context warnings appear for high-risk or uncertain output.
- [ ] Sources and attribution are provided.
- [ ] Confidence or uncertainty is shown.
- [ ] Updates and changes are communicated.
- [ ] Language is plain and honest.
