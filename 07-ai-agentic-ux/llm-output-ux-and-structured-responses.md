# LLM Output UX and Structured Responses

Large language models (LLMs) can produce long, uncertain, or complex output. The UX challenge is to present that output in a way that is scannable, trustworthy, and actionable.

---

## 1. LLM Output Challenges

- **Length**: output can be long and hard to scan.
- **Uncertainty**: the model may be wrong or vague.
- **Monotony**: walls of text are hard to digest.
- **Lack of structure**: raw paragraphs are not always useful.
- **Trust**: users may not know what to believe.

---

## 2. Presenting LLM Output

### Use structure

- Headings, bullets, numbered lists, and tables.
- Highlight key takeaways.
- Break long output into sections.
- Use collapsible details for optional depth.

### Highlight important parts

- Bold key terms and conclusions.
- Use color and icons sparingly.
- Pull out a summary at the top.

### Show confidence

- “This answer is based on 3 documents.”
- “I’m not certain about this part.”
- Use confidence labels where useful.

### Provide sources

- Cite the documents, pages, or data used.
- Link to original sources when possible.
- Let users verify the output.

---

## 3. Structured Response Formats

### Summaries

A short, one-paragraph summary at the top.

- “Three key points: …”
- “Yes / No / Maybe” with reasoning.

### Lists and bullets

Good for steps, ideas, options, or findings.

- Keep bullets parallel.
- Use numbers for ordered steps.
- Limit depth to two levels.

### Tables

Good for comparisons, data, or structured results.

| Option | Pros | Cons |
|--------|------|------|
| A | Fast | Expensive |
| B | Cheap | Slow |

### Cards

Good for items with rich metadata.

- Each card has a title, key facts, and actions.

### Timelines and logs

Good for step-by-step processes or histories.

- Show each step with status and result.

### Code blocks

- Format code with syntax highlighting.
- Make it easy to copy.
- Show language and filename.

---

## 4. Interactive Output

- **Regenerate** if the output is not useful.
- **Edit** the output inline.
- **Copy** content or code.
- **Save** or **export** the response.
- **Thumbs up / down** for feedback.
- **Expand / collapse** for long sections.
- **Follow-up prompts** to continue the conversation.

---

## 5. Error and Uncertainty

- If the model is uncertain, say so.
- If the model cannot answer, explain why.
- If the model hallucinates, help the user verify.
- Do not present uncertain information as fact.

---

## 6. Progressive Disclosure

- Start with the most useful summary.
- Let users expand for more detail.
- Avoid overwhelming with the full output at once.

---

## 7. Accessibility

- Use semantic HTML for headings and lists.
- Ensure text is readable and well-spaced.
- Do not rely on color alone for meaning.
- Provide transcripts for spoken responses.
- Allow users to adjust text size.

---

## 8. Common Mistakes

- Presenting long, unformatted walls of text.
- No sources or attribution.
- Hiding uncertainty.
- Overusing bold or color.
- No way to copy, edit, or save.
- Presenting code without formatting.
- No summary for long responses.
- Outputs that are not scannable.

---

## 9. Checklist

- [ ] Output is structured with headings and lists.
- [ ] A summary is shown for long responses.
- [ ] Key points are highlighted.
- [ ] Sources and citations are provided.
- [ ] Confidence or uncertainty is communicated.
- [ ] Users can copy, edit, and save output.
- [ ] Code is formatted and copyable.
- [ ] Progressive disclosure is used.
- [ ] Output is scannable and accessible.
- [ ] Users can give feedback and regenerate.
- [ ] Errors and limits are clearly stated.
