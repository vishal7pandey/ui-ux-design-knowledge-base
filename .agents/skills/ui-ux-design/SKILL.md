---
name: ui-ux-design
description: Comprehensive UI/UX design knowledge base covering design principles, color theory, typography, component patterns, design systems/tokens, UX process (research, wireframing, prototyping, testing, handoff), accessibility (WCAG), usability heuristics, checklists, and agentic/AI interface design (AX). Use whenever building, reviewing, or redesigning any user interface, evaluating usability, setting up or auditing a design system, choosing colors/fonts/spacing, or designing an AI-powered/agentic product experience.
---

# UI/UX Design Skill

This skill gives you access to a comprehensive UI/UX knowledge base living in this repository. Consult it before making any visual, interaction, accessibility, or agentic-UX decision — do not invent conventions from training-data defaults when this knowledge base already has a documented answer.

## Decision Tree — Which Reference to Consult

| Task | Read |
|---|---|
| Choosing colors, palettes, dark mode | `01-design-principles/color-theory.md` |
| Choosing fonts, type scale, pairing | `01-design-principles/typography.md` |
| Spacing, grids, layout, breakpoints | `01-design-principles/spacing-and-layout.md` |
| Visual hierarchy / what draws the eye | `01-design-principles/visual-hierarchy.md` |
| Any accessibility question | `01-design-principles/accessibility.md` + `05-checklists/accessibility-checklist.md` |
| General design principles / expressive design | `01-design-principles/design-principles.md` |
| Building a specific component (button, form, card, nav, modal, table, feedback/toast, chart) | `02-component-patterns/<component>.md` |
| Design tokens (color/spacing/type/shadow/radius scales) | `03-design-system/design-tokens.md` |
| Component library architecture, props/API conventions, versioning | `03-design-system/component-library.md` |
| Assessing design-system health/maturity | `03-design-system/component-library.md` (6-Dimension Maturity Framework section) |
| Icons | `03-design-system/iconography.md` |
| Motion/animation | `03-design-system/animation.md` |
| User research, personas, journey maps, user panels | `04-ux-process/research.md` |
| Wireframing | `04-ux-process/wireframing.md` |
| Prototyping | `04-ux-process/prototyping.md` |
| Usability testing | `04-ux-process/usability-testing.md` |
| Running a heuristic evaluation / Nielsen's 10 heuristics | `04-ux-process/heuristic-evaluation.md` |
| Design-to-dev handoff, design specs | `04-ux-process/handoff.md` |
| Pre-ship review | `05-checklists/ui-checklist.md`, `05-checklists/ux-checklist.md`, `05-checklists/accessibility-checklist.md` |
| Tool/resource recommendations | `06-resources/tools.md`, `06-resources/inspiration.md` |
| Designing an agentic/AI-powered feature (human-in-the-loop, autonomy levels, transparency) | `07-ai-agentic-ux/agentic-experience-design.md` |
| Designing an AI interface (voice, canvas, adaptive/generative UI, agent workflows) | `07-ai-agentic-ux/ai-interface-patterns.md` |
| Choosing an agentic architecture pattern (routing, reflection, tool use, multi-agent, HITL, guardrails...) | `07-ai-agentic-ux/agentic-design-patterns.md` |
| Understanding AI's real limits for design work / UX-context design | `07-ai-agentic-ux/ai-for-designers.md` |
| Service design when AI agents mediate the experience | `07-ai-agentic-ux/service-design-ai-era.md` |
| Illustration/motion language for an AI product | `07-ai-agentic-ux/ai-illustration-motion.md` |

## Non-Negotiable Rules

1. **Never invent tokens.** If the project has design tokens (check for `DESIGN.md`, a `tokens/` directory, or CSS variables), use them exactly. Only fall back to the scales in `03-design-system/design-tokens.md` if the project has none yet — and if so, propose establishing them rather than hardcoding values.
2. **Accessibility is mandatory, not a nice-to-have.** Check color contrast (WCAG AA: 4.5:1 text, 3:1 UI components), keyboard navigability, and semantic HTML/ARIA for every UI you generate. Reference `01-design-principles/accessibility.md`.
3. **Run new patterns against Nielsen's 10 heuristics** (`04-ux-process/heuristic-evaluation.md`) before considering a UI finished — especially visibility of system status, error prevention, and recognition over recall.
4. **Avoid generic "AI slop" aesthetics.** No default purple-gradient-on-white, no reflexive Inter/Roboto/Arial fallback, no cookie-cutter card-grid layouts, unless the project's existing design language calls for it. Commit to one clear, intentional aesthetic direction rather than a timid, generic one — see `01-design-principles/design-principles.md` (Expressive Design and True-over-New sections).
5. **For agentic/AI features**, apply the AX principles from `07-ai-agentic-ux/agentic-experience-design.md`: design an explicit human-in-the-loop checkpoint for any consequential action, make agent reasoning visible, and make actions reversible.
6. **Match implementation fidelity to the actual open question.** If the real unknown is structural/architectural (not visual), don't jump straight to polished high-fidelity output — see `07-ai-agentic-ux/ai-for-designers.md`.

## Workflow

1. Identify the task category using the decision tree above.
2. Read the specific reference file(s) — don't guess when documented guidance exists in this repo.
3. If building a component, cross-check `02-component-patterns/` for the interaction pattern and `03-design-system/component-library.md` for prop/state/API conventions.
4. If the project already has its own design tokens or a `DESIGN.md`/style guide, those take precedence over this repo's defaults — this repo fills gaps, it doesn't override an established project system.
5. Before finishing, run the relevant checklist from `05-checklists/`.
6. If the feature involves an AI agent acting autonomously, additionally run it against `07-ai-agentic-ux/agentic-design-patterns.md`'s "Designer's Checklist for Any Agentic Feature."
