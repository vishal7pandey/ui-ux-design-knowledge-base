# AI Bias and Fairness in UX

AI systems can reflect and amplify bias. UX designers play a role in identifying, surfacing, and reducing unfair outcomes in AI products.

---

## 1. What Is AI Bias?

Bias is a systematic error that leads to unfair outcomes for certain groups. It can come from:

- **Training data**: unrepresentative or historical data.
- **Labels**: biased human judgments.
- **Design choices**: what the product optimizes for.
- **User feedback**: over-representing some voices.
- **Context**: applying the model where it was not tested.

---

## 2. Types of Bias

### Representation bias

- Some groups are missing or underrepresented in the data.
- The model performs worse for those groups.

### Historical bias

- Past discrimination is baked into the data.
- The model reproduces old patterns.

### Measurement bias

- The way success is measured is flawed.
- Example: a model predicts success but the “success” label is biased.

### Aggregation bias

- One model is used for everyone, but different groups have different needs.

### User interaction bias

- Users from different groups use the product differently.
- Feedback loops favor certain behaviors.

---

## 3. Fairness Principles

### Equitable performance

The AI should work well for all relevant groups.

### Equal opportunity

All users have access to the same benefits.

### Transparency

Users understand how decisions are made and can challenge them.

### Accountability

There is a clear path to report and fix unfair outcomes.

### Inclusive design

Diverse users are involved in research, design, and testing.

---

## 4. UX Patterns for Fairness

### Demographic disclosure

- Explain who the model was trained on.
- Note if it may not work for some groups.

### Outcome explanation

- Show why a decision or recommendation was made.
- Help users identify when the result is wrong or unfair.

### Human review

- Let users appeal or request review.
- Provide an escalation path.

### Feedback and reporting

- Let users report biased or unfair output.
- Show that the report is taken seriously.

### Inclusive defaults

- Use defaults that do not assume a single norm.
- Support diverse names, formats, and languages.

---

## 5. Design for Fairness

- Include diverse users in research.
- Test with underrepresented groups.
- Review outputs for harmful stereotypes.
- Avoid defaults that exclude.
- Let users correct inaccurate results.
- Monitor for biased patterns in usage data.
- Build feedback loops for affected users.

---

## 6. Common Mistakes

- Assuming data is neutral.
- Testing only with the majority group.
- Hiding how decisions are made.
- No way to challenge or correct outcomes.
- Using single defaults for all users.
- Not monitoring for bias after launch.
- Treating fairness as a one-time check.

---

## 7. Checklist

- [ ] Diverse users are included in research and testing.
- [ ] Training data and limitations are disclosed.
- [ ] Model performance is evaluated across groups.
- [ ] Outcomes are explainable.
- [ ] Users can challenge and correct decisions.
- [ ] Bias can be reported and reviewed.
- [ ] Defaults and options are inclusive.
- [ ] Outputs are checked for harmful stereotypes.
- [ ] Bias is monitored after launch.
- [ ] The team has a plan for responding to fairness issues.
