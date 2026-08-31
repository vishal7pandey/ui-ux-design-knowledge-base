# Core Design Principles

## 1. Clarity Over Cleverness

The user should never have to think about how to use your interface.

- **Be obvious.** A button should look like a button. A link should look like a link.
- **Use familiar patterns.** Don't reinvent the wheel — users have expectations from other apps.
- **Write clear labels.** "Save" is better than "Persist Changes." "Delete" is better than "Remove from System."

## 2. Consistency

Consistency builds trust and reduces cognitive load.

- **Visual consistency:** Same colors, fonts, spacing, and component styles throughout.
- **Functional consistency:** Same actions produce same results everywhere.
- **Internal consistency:** Your app follows its own rules.
- **External consistency:** Your app follows platform conventions (iOS, Android, Web).

## 3. Feedback

Every action should have a reaction.

- **Immediate:** Button press state, hover states, click animations.
- **Near-term:** Loading spinners, progress bars, success toasts.
- **Long-term:** Confirmation emails, status updates, notifications.

### Feedback Types

| Action | Feedback |
|---|---|
| Button click | Visual press state + action executes |
| Form submit | Loading state → success/error message |
| Data loading | Skeleton screen or spinner |
| Error occurs | Clear error message with recovery path |
| Success | Confirmation toast or inline message |

## 4. Efficiency

Design for the user who uses your product every day.

- **Keyboard shortcuts** for power users.
- **Smart defaults** that work for 80% of users.
- **Batch operations** when users manage multiple items.
- **Remember state** — don't make users re-enter or re-select.

## 5. Error Prevention & Recovery

### Prevention
- Disable invalid actions (grayed-out buttons).
- Use input constraints (date pickers, dropdowns instead of free text).
- Confirm destructive actions.
- Validate inline, not just on submit.

### Recovery
- Error messages should be: **specific**, **human**, **actionable**.
- Bad: "Invalid input."
- Good: "Please enter a valid email address (e.g., name@example.com)."
- Always provide a way forward: undo, retry, contact support.

## 6. Hierarchy & Focus

Guide the user's eye to what matters most.

- **One primary action** per screen or section.
- **Visual weight** communicates importance (size, color, contrast).
- **Whitespace** separates and groups related content.
- **Progressive disclosure** — show details only when needed.

## 7. Accessibility Is Not Optional

Design for everyone, including users with disabilities.

- Sufficient color contrast (WCAG AA minimum).
- Keyboard navigability for all interactive elements.
- Screen reader support with proper ARIA labels.
- Don't rely on color alone to convey meaning.
- See [accessibility.md](./accessibility.md) for full guidelines.

## 8. Simplicity

> "Perfection is achieved not when there is nothing more to add, but when there is nothing left to take away." — Antoine de Saint-Exupéry

- **Remove** everything that isn't necessary.
- **Hide** what's rarely needed (advanced settings, secondary actions).
- **Displace** what can be moved to a secondary screen.
- **Minimize** cognitive load at every step.

## 9. Responsive & Adaptive

- Design for all screen sizes: mobile, tablet, desktop.
- Touch targets minimum 44×44px on mobile.
- Content should reflow, not just scale.
- Prioritize content for smaller screens — what's essential?

## 10. Performance Is UX

- A fast app feels better. Period.
- Perceived performance matters: skeletons, optimistic updates, transitions.
- Aim for <100ms interaction response time.
- Lazy load images and non-critical content.

---

## Principle Quick Reference

| Principle | Key Question |
|---|---|
| Clarity | "Would a new user understand this in 5 seconds?" |
| Consistency | "Does this match patterns used elsewhere in the app?" |
| Feedback | "Does the user know what just happened?" |
| Efficiency | "Can a power user do this faster?" |
| Error Prevention | "Can the user make a mistake here? How do I prevent it?" |
| Hierarchy | "What's the most important thing on this screen?" |
| Accessibility | "Can everyone use this, regardless of ability?" |
| Simplicity | "What can I remove without losing function?" |
| Responsive | "Does this work on a phone? A 4K monitor?" |
| Performance | "Does this feel instant?" |

---

## 11. Expressive Design (Research-Backed)

Google's Material 3 Expressive update is the most-researched design system change to date (46 studies, 18,000+ participants). Its core finding: **well-applied emotional/expressive design measurably improves both preference and usability** — it isn't a tradeoff between "pretty" and "usable."

### What "Expressive" Means
Expressive design uses **color, shape, size, motion, and containment** deliberately to:
- Draw attention to what matters (key actions stand out)
- Group related elements visually
- Make the interface feel energetic, modern, and human — not just "clean"

### The Research Findings
| Finding | Result |
|---|---|
| **Preference** | Up to 87% preference among 18–24 year-olds; net positive across all age groups |
| **Attribute ratings** | Higher scores for "energetic," "emotive," "positive vibe," "creative," "playful," "friendly" |
| **Desirability** | +32% subculture perception, +34% modernity, +30% "rebellious"/bold perception |
| **Task speed** | Key UI elements spotted up to **4× faster** with expressive treatments (larger buttons, secondary color, strategic placement) |
| **Age equity** | Expressive design nearly erased the age gap in visual search speed — older users (45+) matched younger users' fixation times |
| **Accessibility** | Larger touch targets and high-contrast containment improved usability for users with varying visual/motor abilities |

### When Expressive Design Backfires
Expressive ≠ ignoring UX fundamentals. Two documented failure cases:
- Replacing a familiar vertical list with a decorative, unlabeled grid of album art *looked* modern but usability scores dropped — users couldn't recognize it as a playlist.
- Removing text labels from action buttons (for a "cleaner" look) decreased usability, even though it tested as more visually appealing.

**Rule: no amount of expressive polish compensates for broken core functionality or removed clarity.**

### Practical Guidance
1. **Start from user need**, not visual trend — expressive tactics amplify a good structure, they don't fix a bad one.
2. **Respect established patterns.** Familiar UI paradigms (lists, standard nav, labeled buttons) should stay recognizable even when reskinned expressively.
3. **A minority of users prefer calm, low-intensity UI** — segment and test rather than assuming universal appeal.
4. **Iterate with real research** — eye tracking, sentiment surveys, and usability testing, not just aesthetic review.
5. **Follow accessibility standards regardless of style** — contrast, screen reader support, and navigation clarity are non-negotiable.

---

## 12. True Over New

> "I just reject the idea that you've got to be new every time. I think it's more important to be true than new." — David Reinfurt, designer

Not every design problem needs a novel solution. Chasing novelty for its own sake produces "AI slop"-style sameness or brittle, over-clever interfaces. Instead:

- **Trust intuition.** Individual perspective and instinct are part of the craft — don't let process or data replace judgement entirely.
- **Design lives closer to daily life than art.** Unlike art, which invites contemplative distance, design is imminent and functional — "the door handle you just pushed." It's harder to ignore, and gets punished faster when it's wrong.
- **A little dissonance is often good.** Perfectly smooth, invisible design can feel sterile. The designs people remember usually have *some* imperfection, texture, or friction that makes them feel considered rather than generated.
- **Cooperation beats compromise.** The best outcomes come from genuine coöperation between collaborators — not from splitting the difference between competing opinions.
- **Reexploring old ideas is valid.** A simplified, well-worn form (like Enzo Mari's "La Mela") can still yield infinitely fresh experiences — you don't need to reinvent the fundamentals to create something meaningful.
