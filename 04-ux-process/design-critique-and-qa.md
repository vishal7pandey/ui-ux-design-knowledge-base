# Design Critique and QA

Design critique and QA are how teams catch issues before they reach users. Critique improves the work; QA confirms the build matches the intent.

---

## 1. Design Critique

A design critique is a structured conversation about whether a design meets its objectives. It is not about judging the designer; it is about improving the work.

### When to run a critique

- Early, when changes are cheap.
- At key milestones: wireframes, high-fidelity, before handoff.
- Repeatedly as the design evolves.

### Roles

| Role | Responsibility |
|------|----------------|
| **Presenter** | Provides context, goals, and walkthrough. |
| **Facilitator** | Keeps the discussion on track and on time. |
| **Note-taker** | Captures insights and action items. |
| **Critiquers** | Provide feedback tied to user or business goals. |

### Rules for useful feedback

- Link feedback to user or business goals.
- Ask questions before giving solutions.
- Be specific: what, where, why.
- Avoid directives and personal preferences.
- Focus on the work, not the person.

### Before the critique

- Define the scope.
- Share context and objectives in advance.
- Explain what feedback is needed.
- Assign roles.

### During the critique

- Walk through the design from the user’s starting point.
- Keep discussion inside the scope.
- Capture questions and risks.
- Timebox each contributor.

### After the critique

- Summarize decisions and actions.
- Assign owners and deadlines.
- Share notes with the team.

---

## 2. Design QA

Design QA is the final check that the implemented design matches the intended design. It happens after development and before release.

### Why it matters

- Catches visual and interaction issues before users do.
- Reduces revisions after launch.
- Builds trust between design and engineering.

### When to do design QA

- After a feature is built but before it ships.
- On critical user flows.
- On design-system component updates.

---

## 3. Design QA Checklist

### 3.1 Foundations

- [ ] Fonts, sizes, weights, and line heights match the type scale.
- [ ] Colors use design tokens, not hard-coded values.
- [ ] Spacing follows the 8px grid.
- [ ] Contrast meets WCAG 2.2 AA standards.
- [ ] Touch targets are at least 44×44dp.

### 3.2 Components

- [ ] All states are present: default, hover, active, focus, disabled, error, loading.
- [ ] Correct component variant is used.
- [ ] No detached or duplicate components.
- [ ] Component slots and content are used as intended.

### 3.3 Layout

- [ ] Alignment is consistent across screens.
- [ ] Responsive behavior matches the design.
- [ ] Content wraps and truncates correctly.
- [ ] No unexpected layout shifts.

### 3.4 Interactions

- [ ] Hover, focus, and active states are visible.
- [ ] Transitions and animations are smooth.
- [ ] Loading, empty, and error states are implemented.
- [ ] Focus order is logical.

### 3.5 Accessibility

- [ ] Keyboard navigation works.
- [ ] Screen-reader behavior is correct.
- [ ] Alt text is present for images and icons.
- [ ] ARIA labels are used where needed.
- [ ] Color is not the only indicator of state.

### 3.6 Copy

- [ ] All placeholder text is removed.
- [ ] Microcopy matches the design and style guide.
- [ ] Error and empty states use the right copy.
- [ ] No truncation or overflow issues.

### 3.7 Edge cases

- [ ] Empty states are handled.
- [ ] Error states are handled.
- [ ] Loading states are handled.
- [ ] Long content, large numbers, and long names are tested.
- [ ] No-internet and slow-network scenarios are considered.

---

## 4. Severity Levels

| Level | Meaning | Example |
|-------|---------|---------|
| **Blocker** | Cannot ship. Fails WCAG, breaks a flow, or causes data loss. | Form cannot be submitted with a keyboard. |
| **Major** | Visually or functionally incorrect. Should be fixed before launch. | Button is the wrong color across all states. |
| **Minor** | Polish issue. Can ship with a follow-up ticket. | Slight misalignment on one screen. |
| **Trivial** | Cosmetic, no user impact. | Layer name in Figma is messy. |

---

## 5. Tools and Process

### For design critique

- Figma comments and annotations.
- Miro or FigJam for collaborative sessions.
- Loom for async walkthroughs.
- A shared critique brief.

### For design QA

- Figma Dev Mode for spec comparison.
- Browser dev tools for CSS inspection.
- BrowserStack or device testing for responsive checks.
- Screen readers and keyboard-only testing.
- Color contrast analyzers.

### Process

1. Designer files a design QA ticket.
2. Designer or QA specialist reviews the build against the checklist.
3. Issues are logged with screenshots and severity.
4. Engineer fixes and reassigns.
5. Designer verifies fixes before sign-off.
6. Product gives final approval.

---

## 6. Common Mistakes

- Skipping critique because the timeline is tight.
- Turning critique into a debate about taste.
- Doing QA only for the happy path.
- Failing to test on real devices.
- Not documenting QA findings as trackable tickets.
- Leaving QA to the last minute.

---

## 7. Checklist

- [ ] Critique has clear scope, goals, and roles.
- [ ] Feedback is tied to user or business goals.
- [ ] Notes are captured and shared.
- [ ] QA is performed before release.
- [ ] QA checklist is adapted to the project.
- [ ] Issues are triaged by severity.
- [ ] Findings become trackable tickets.
- [ ] Fixes are verified before sign-off.
