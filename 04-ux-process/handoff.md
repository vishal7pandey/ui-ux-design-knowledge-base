# Design to Development Handoff

## What Is Handoff?

Handoff is the process of transferring design specifications from designers to developers. A good handoff ensures the built product matches the design with minimal back-and-forth.

## Why Handoff Fails

| Problem | Consequence |
|---|---|
| Vague specs | Developers guess, result doesn't match |
| Missing states | Error, empty, loading states not designed |
| No responsive specs | Mobile looks broken |
| Inconsistent tokens | Hardcoded values instead of design tokens |
| No asset export | Developers hunt for icons/images |
| Outdated files | Developer builds from old version |
| No communication | Questions pile up, momentum stalls |

## Handoff Checklist

### Design Files
- [ ] All screens designed (including responsive breakpoints)
- [ ] All states covered (default, hover, focus, active, disabled, error, empty, loading)
- [ ] Components use the design system (no one-off styles)
- [ ] Design tokens applied (not hardcoded values)
- [ ] File is organized (pages named, layers grouped)
- [ ] File is up to date (no outdated versions)

### Interactions & Animations
- [ ] Prototype linked (clickable flow)
- [ ] Transitions documented (type, duration, easing)
- [ ] Micro-interactions specified (hover, press states)
- [ ] Scroll behavior noted (sticky, parallax, infinite scroll)
- [ ] Edge case behaviors documented

### Assets
- [ ] Icons exported (SVG, optimized)
- [ ] Images exported (WebP/AVIF, correct resolution)
- [ ] Fonts specified (family, weights, fallbacks)
- [ ] Logos exported (SVG, all variants)

### Specs
- [ ] Spacing documented (padding, margins, gaps)
- [ ] Typography specs (size, weight, line height, letter spacing)
- [ ] Color values provided (hex or token references)
- [ ] Border radius and shadows specified
- [ ] Responsive breakpoints defined
- [ ] Grid/layout system documented

### Content
- [ ] Real or realistic content used (not lorem ipsum)
- [ ] Character limits noted
- [ ] Dynamic content variations considered (short/long text)
- [ ] Empty states designed
- [ ] Error messages written

### Accessibility
- [ ] Focus states designed
- [ ] Color contrast verified (WCAG AA)
- [ ] Alt text written for images
- [ ] ARIA labels specified for icon-only buttons
- [ ] Keyboard navigation flow documented
- [ ] Screen reader behavior noted

## Handoff Documentation

### Design Spec Document
A written document that supplements the design files:

```markdown
# Feature: User Profile Page

## Overview
Redesigned profile page with editable fields, avatar upload,
and activity timeline.

## Screens
1. Profile view (default)
2. Profile edit mode
3. Avatar upload (modal)
4. Profile (empty state - new user)

## Responsive
- Mobile: 375px (single column)
- Tablet: 768px (two column)
- Desktop: 1024px+ (two column with sidebar)

## Interactions
- Click "Edit Profile" → switches to edit mode (inline)
- Avatar click → opens upload modal
- Save button → validates → shows toast → returns to view mode
- Cancel button → confirms discard → returns to view mode

## Animations
- Edit mode transition: 200ms fade
- Modal open: 250ms scale + fade
- Toast: 300ms slide up, auto-dismiss 3s

## Edge Cases
- Name: max 50 chars, truncate with ellipsis
- Bio: max 200 chars, show counter
- No activity: show empty state with CTA
- Avatar upload fails: show error in modal

## Accessibility
- All form fields have labels
- Avatar upload has keyboard alternative
- Color contrast: AA verified
- Focus order: top to bottom
```

## Figma Handoff Features

### Dev Mode
Figma's Dev Mode provides developers with:
- Inspect panel (spacing, colors, typography, borders)
- Code export (CSS, iOS, Android)
- Asset export (SVG, PNG)
- Dev resources links

### Tips for Figma Handoff
1. **Use Auto Layout** — generates proper flexbox-like specs
2. **Use Components** — developers can reference the design system
3. **Use Variables** — maps to design tokens
4. **Name layers clearly** — "Button/Primary" not "Rectangle 47"
5. **Organize pages** — "✅ Ready for Dev", "🔄 In Progress", "📝 Notes"
6. **Mark ready screens** — use a ✅ emoji or status label
7. **Pin comments** — leave spec notes as comments on the canvas

## Communication During Handoff

### Kickoff Meeting
- Walk through the design together
- Explain key decisions and trade-offs
- Discuss technical constraints
- Identify potential challenges
- Agree on timeline

### Ongoing Communication
- **Slack/Teams channel** for the feature
- **Daily or weekly check-ins** during implementation
- **Design review** when first build is ready
- **QA process** — designer reviews the built version

### Design Review
When the developer has a working build:
1. Designer reviews against the design files
2. Note discrepancies (spacing, color, typography)
3. Test interactions and states
4. Test responsive behavior
5. Test accessibility
6. Provide feedback in a shared document

## Common Handoff Gaps

| Gap | Solution |
|---|---|
| "What about the empty state?" | Design all states before handoff |
| "How does this animate?" | Prototype the animation, document timing |
| "What's the max text length?" | Specify character limits in the design |
| "Does this need to be accessible?" | Always specify accessibility requirements |
| "What happens on error?" | Design error states and messages |
| "How does this work on mobile?" | Design all breakpoints |
| "Where are the icons?" | Export all assets before handoff |

## Tools

| Tool | Purpose |
|---|---|
| **Figma Dev Mode** | Design inspection, code export |
| **Zeplin** | Design specs, style guides |
| **Storybook** | Component documentation, visual testing |
| **Zeroheight** | Living style guide (Figma + code) |
| **Notion/Confluence** | Spec documentation |
| **Linear/Jira** | Task tracking, linking to designs |

## Best Practices

### For Designers
- **Design all states** — not just the happy path
- **Use the design system** — don't create one-off styles
- **Be available** — answer questions promptly during implementation
- **Review the build** — don't disappear after handoff
- **Document decisions** — explain why, not just what

### For Developers
- **Read the specs** — don't just eyeball the design
- **Ask questions early** — don't wait until you're stuck
- **Use design tokens** — don't hardcode values
- **Flag gaps** — tell the designer what's missing
- **Build incrementally** — get a rough version up, then refine together

### For Both
- **Collaborate, don't throw over the wall** — handoff is ongoing, not one-time
- **Use shared tools** — Figma, Storybook, shared docs
- **Respect each other's expertise** — designers design, developers build, both have valid input
- **Test the result** — compare built version to design, fix discrepancies

---

## Design Specs: The Two-Part Contract

A **design spec** is the document (or set of linked artifacts) that gives developers everything they need to implement a design correctly — functionality, behavior, and appearance — without guessing. Clear specs prevent the classic "you review it with the dev team and they say it isn't possible" failure mode, by surfacing feasibility and technical constraints *before* build starts, not after.

Design specs consistently break down into **two components** that must both be present:

### Part 1: The Design File
What designers typically think of as "the spec" — the design file itself (Figma, etc.), broken down into consumable pieces for developers. Should include:
- Interactive elements and flows
- Visual design, layout (grid system, breakpoints)
- Content specifics
- Special accessibility needs

### Part 2: The Development Issue
The contextual "ticket" that wraps the design file with the information developers need to understand *why*, not just *what*. Typically owned by the product owner or tech lead, and should include:
- **Goal** of the design
- **Project scope**
- **Functional and non-functional requirements**
- **Potential risks and mitigations**

> Many development teams treat the development issue as a **contract** between design and engineering — what's outlined here is what gets built. Make sure it accurately reflects what you actually need delivered.

### What a Good Spec Looks Like
- Scoped tightly enough that a developer can understand the full need and implement it in a reasonable time (don't bundle 10 unrelated changes into one spec).
- Includes sufficient context up front: design goal, scope, and any preliminary research — not just the visuals.
- Links directly to the design file, with basic implementation notes restated in the ticket itself (don't make developers hunt across tools).
- Screen relationships and flows are annotated in the design file (e.g., how different mobile screens connect), so developers can reason about the full user journey — not just isolated screens.

### Why Both Parts Matter
A design file alone tells developers *what it should look like*. A development issue alone tells them *why it matters and what the constraints are*. Skipping either half reproduces the classic handoff failure: technically-correct-but-wrong-context builds, or beautiful specs that turn out to be infeasible. Pair this with the full [Handoff Checklist](#handoff-checklist) above before considering a design "dev-ready."
