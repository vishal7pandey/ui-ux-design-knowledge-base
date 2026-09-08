# Prompt Engineering for Product Designers

Prompt engineering is the practice of writing clear, effective instructions for AI models. For product designers, it is a tool for exploration, synthesis, prototyping, and communication.

---

## 1. Why Designers Should Learn Prompt Engineering

- Generate and compare ideas quickly.
- Explore content and copy options.
- Summarize research and feedback.
- Create prototypes and mock content.
- Communicate design intent to engineers and stakeholders.
- Test how users might interact with AI features.

---

## 2. Prompt Structure

A good prompt has context, instruction, and constraints.

```
[Role] + [Context] + [Task] + [Format] + [Constraints]
```

Example:

```
You are a UX writer. Our product is a B2B project management tool. Write 5 short, clear labels for a button that creates a new project. Use action verbs. Keep each under 3 words.
```

---

## 3. Prompt Patterns for Designers

### Persona and role

Tell the AI who it is and what perspective to take.

```
Act as a senior UX researcher reviewing this interview transcript...
```

### Constraints

Limit the output by length, tone, format, or scope.

```
...in a 50-word summary for a mobile notification.
```

### Few-shot prompting

Give examples of the desired output.

```
Here are two examples of onboarding copy:
- Example 1: ...
- Example 2: ...
Write a third for [new context].
```

### Chain-of-thought

Ask the AI to think step by step.

```
Analyze this user flow step by step. For each step, identify the potential usability issue and suggest a fix.
```

### Reframe and iterate

- Start broad, then narrow.
- Ask for variations.
- Ask the AI to critique its own output.

---

## 4. Design Use Cases

### User research synthesis

```
Summarize the top 5 pain points from these 12 interview notes. Group by theme.
```

### Copy exploration

```
Write 10 variations of a button label for saving a draft. Friendly, professional tone.
```

### Concept ideation

```
Generate 5 mobile onboarding patterns for a finance app. Focus on building trust.
```

### Competitive analysis

```
Compare the navigation patterns of Asana, Trello, and Monday.com. Include pros and cons.
```

### Accessibility checks

```
Review this UI copy for inclusivity and clarity. Highlight issues and suggest improvements.
```

---

## 5. Best Practices

- Be specific. Vague prompts produce vague output.
- Define the format you want.
- Use examples when the style matters.
- Iterate. The first result is rarely the best.
- Verify the output, especially for facts.
- Ask for multiple options to compare.
- Use the AI as a thinking partner, not a final authority.

---

## 6. Common Mistakes

- Assuming the AI knows the context.
- Accepting the first output without iteration.
- Not constraining length or format.
- Asking for too much in one prompt.
- Using the AI for tasks that need real user data.
- Not checking for bias, stereotypes, or inaccuracies.
- Copying generated content without review.

---

## 7. Prompt Library

Create a personal or team prompt library for reuse.

| Task | Prompt |
|------|--------|
| User flow critique | “Review this flow and identify usability issues step by step.” |
| Copy options | “Write 10 short, friendly [label] options for [action].” |
| Research synthesis | “Synthesize these notes into 5 themes with quotes.” |
| Accessibility review | “Check this copy for inclusive language and readability.” |
| Design rationale | “Write a brief design rationale for [decision] aimed at [audience].” |

---

## 8. Checklist

- [ ] Prompt includes role, context, task, format, and constraints.
- [ ] Output is verified, not blindly used.
- [ ] Multiple options are generated for comparison.
- [ ] Prompt is iterated to improve results.
- [ ] Generated content is checked for bias and accuracy.
- [ ] Prompts are saved in a reusable library.
- [ ] AI is used as a thinking partner, not a replacement for judgment.
