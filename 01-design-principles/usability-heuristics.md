# Usability Heuristics

Heuristics are broad rules of thumb for evaluating and improving interfaces. This guide covers the foundational principles that still apply to every platform, including AI-driven and agentic interfaces.

---

## 1. Visibility of System Status

**Principle**: The system should always keep users informed about what is going on, through appropriate feedback within a reasonable time.

### What it means in practice

- Show loading states, progress bars, and skeleton screens while content loads.
- Confirm that an action was received (button loading state, toast, inline checkmark).
- Display current step in multi-step flows.
- For agents: show thinking, tool calls, and intermediate state.

### Agentic extension

Agents spend time reasoning and acting. A status that says only “Loading...” is not enough. Surface:

- What the agent is doing now
- What it has done
- Estimated time remaining
- Whether it is waiting on user input

---

## 2. Match Between System and the Real World

**Principle**: The system should use words, phrases, and concepts familiar to the user, not internal system terms.

### What it means in practice

- Use plain language: “Send message” not “POST /message.”
- Mirror the user’s mental model, not the database schema.
- Icons and labels should match real-world conventions (trash = delete, magnifying glass = search).

### Agentic extension

Agents should translate inferred user intent into human-readable intent previews: “I will check eligibility, submit the refill request, and schedule a follow-up if required.”

---

## 3. User Control and Freedom

**Principle**: Users need clearly marked exits from unwanted states and the ability to undo or reverse actions.

### What it means in practice

- Provide cancel, back, and close affordances.
- Support undo for reversible actions.
- Allow users to exit wizards and onboarding without losing progress.
- Offer “Don’t ask me again” only after the first few confirmations.

### Agentic extension

- Pause, cancel, or override agent actions at any time.
- Allow rollback of agent-initiated changes.
- Provide approval gates for high-impact actions.

---

## 4. Consistency and Standards

**Principle**: Users should not have to wonder whether different words, situations, or actions mean the same thing.

### What it means in practice

- Use the same labels and icons for the same actions across the product.
- Follow platform conventions (web, iOS, Android, Windows).
- Keep interaction patterns stable: the same button shape should behave the same way.

### Agentic extension

Agents should have consistent personality, tone, and interaction style across sessions and contexts. Capabilities and boundaries should be described in the same way everywhere.

---

## 5. Error Prevention

**Principle**: Better than good error messages is a design that prevents problems from occurring.

### What it means in practice

- Disable submit until required fields are valid.
- Use constraints: date pickers, numeric inputs, autocomplete.
- Confirm destructive actions with a clear summary of consequences.
- Provide inline validation before submission.

### Agentic extension

- Show action previews before agents execute irreversible operations.
- Validate inferred intent with the user.
- Use guardrails to prevent agents from accessing sensitive data or systems.

---

## 6. Recognition Rather than Recall

**Principle**: Minimize the user’s memory load by making objects, actions, and options visible.

### What it means in practice

- Show recently used items, recent searches, and history.
- Use autocomplete and suggestion chips.
- Keep navigation and important actions visible, not buried in menus.

### Agentic extension

- Surface relevant context the agent is using (retrieved sources, prior conversation).
- Make agent capabilities visible, not hidden behind commands the user must remember.

---

## 7. Flexibility and Efficiency of Use

**Principle**: Accelerators and shortcuts can speed up expert users without hindering novices.

### What it means in practice

- Keyboard shortcuts for common actions.
- Bulk operations, templates, and saved views.
- Customizable dashboards and pinned items.
- Command palettes for power users.

### Agentic extension

- Allow users to define preferences, custom prompts, and reusable workflows.
- Support progressive trust so frequent actions become faster over time.

---

## 8. Aesthetic and Minimalist Design

**Principle**: Interfaces should not contain information that is irrelevant or rarely needed.

### What it means in practice

- Remove decorative UI that does not serve a purpose.
- Use whitespace, hierarchy, and grouping to reduce cognitive load.
- Avoid unnecessary options and noise.

### Agentic extension

Use progressive disclosure: show the final answer first, reasoning on demand, and full trace only for debuggers.

---

## 9. Help Users Recognize, Diagnose, and Recover from Errors

**Principle**: Error messages should be expressed in plain language, indicate the problem precisely, and suggest a constructive solution.

### What it means in practice

- “Please enter a valid date” not “Error 400: invalid_payload.”
- Show the error near the relevant field.
- Provide a clear path to fix the problem.

### Agentic extension

Agent errors should be specific and actionable:

- “I couldn’t access your calendar because it requires permission. Open settings to connect it.”
- “I found conflicting instructions. Which of these did you mean?”

---

## 10. Help and Documentation

**Principle**: Even with a perfect interface, documentation may be needed. It should be easy to search, focused on the user’s task, and not too large.

### What it means in practice

- Contextual tooltips and inline help.
- Searchable help center.
- Onboarding tooltips for first use.
- Empty states that explain how to get started.

### Agentic extension

- Agent capability descriptions (e.g., “I can read your email but not your bank.”).
- Example prompts and sample tasks.
- Explainability of agent decisions and reasoning.

---

## Conducting a Heuristic Evaluation

### What it is

A small team of evaluators inspects an interface and judges it against a set of heuristics to find usability problems.

### Steps

1. **Choose scope**: a few representative flows or screens.
2. **Assign evaluators**: 3–5 reviewers, including at least one with UX expertise.
3. **Review individually**: each evaluator walks through the interface against each heuristic.
4. **Record findings**: note the heuristic violated, the severity, and a recommendation.
5. **Aggregate and prioritize**: group duplicate findings and rank by severity.

### Severity scale

| Rating | Meaning |
|--------|---------|
| **0** | Not a problem |
| **1** | Cosmetic issue; does not need fixing unless time permits |
| **2** | Minor problem; low priority |
| **3** | Major problem; important to fix |
| **4** | Catastrophic; must fix before release |

### Heuristic evaluation checklist

- [ ] Status is visible at all times
- [ ] Language matches the user’s mental model
- [ ] Users can undo, cancel, or escape
- [ ] Patterns and labels are consistent
- [ ] Errors are prevented before they happen
- [ ] Information is visible rather than memorized
- [ ] Shortcuts exist for expert users
- [ ] Interface is clean and uncluttered
- [ ] Error messages are clear and actionable
- [ ] Help is available, searchable, and task-focused

---

## Heuristics in the Agentic Era

Nielsen’s heuristics remain relevant because they describe human needs, not technology. For agentic systems, the same principles apply with extra emphasis on:

- **Visibility of system status**: agents must show what they are doing and why.
- **User control and freedom**: agents act on the user’s behalf, so pause, undo, and override are critical.
- **Error prevention**: validate inferred intent and prevent consequential mistakes.
- **Recognition over recall**: make capabilities, sources, and reasoning visible.
- **Error recovery**: when agents are wrong, the fix must be clear and accessible.
