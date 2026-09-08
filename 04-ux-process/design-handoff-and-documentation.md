# Design Handoff and Documentation

A good handoff turns design intent into production reality. It is the bridge between design and engineering, and it is where many products lose fidelity.

---

## 1. What to Include in a Handoff

A complete handoff package should include:

1. **Designs** — screens, flows, and states at every breakpoint.
2. **Prototypes** — interactive flows for key user journeys.
3. **Specifications** — spacing, sizing, typography, colors, tokens.
4. **Assets** — icons, illustrations, images, and fonts.
5. **Component mapping** — which design-system components to use.
6. **Behavior notes** — interactions, transitions, loading, error, and empty states.
7. **Accessibility notes** — focus order, ARIA, contrast, keyboard behavior.
8. **Edge cases** — empty, loading, error, partial, and max-length states.
9. **Context and rationale** — why the design works the way it does.

---

## 2. Design Specs

### Layout and spacing

- Use an 8px grid.
- Annotate padding, margins, and gaps.
- Show responsive behavior across breakpoints.
- Indicate max-width, alignment, and stacking order.

### Typography

- Font family, size, weight, line height, letter spacing.
- Heading and body scales.
- Token names from the design system.

### Color

- Token names, not just hex values.
- Light and dark mode values.
- State colors: default, hover, active, disabled, error, success.

### Components

- Reference the component library.
- Note variants and states.
- Include prop names and accepted values.

---

## 3. Interactive Prototypes

- Link key user flows: happy path, error path, edge cases.
- Show micro-interactions and transitions.
- Include mobile and desktop versions.
- Keep prototypes focused; do not prototype every screen.

---

## 4. Behavior Notes

For each interactive element, document:

- **Default state**: how it looks before interaction.
- **Hover state**: cursor, color, scale, shadow.
- **Focus state**: visible ring, keyboard path.
- **Active / pressed state**: visual feedback.
- **Disabled state**: appearance and interaction.
- **Loading state**: spinner, skeleton, progress.
- **Error state**: message, recovery.
- **Empty state**: copy and CTA.

---

## 5. Accessibility Notes

- Semantic HTML recommendations.
- ARIA roles and labels where native semantics are not enough.
- Focus order and focus management.
- Keyboard shortcuts and operation.
- Color contrast and non-color indicators.
- Alt text for images and icons.
- Screen-reader behavior for dynamic content.

---

## 6. Edge Cases

Designers often ship the happy path and forget the rest. Document:

- Empty, loading, and error states.
- First-time use vs. returning use.
- Minimum and maximum content length.
- Long names, large numbers, missing images.
- Offline or slow network.
- Unauthorized or partially authorized access.

---

## 7. Handoff Tools

| Tool | Best for |
|------|----------|
| **Figma Dev Mode** | Specs, assets, CSS, component inspection. |
| **Figma / Zeplin** | Redlining, asset export, design tokens. |
| **Storybook** | Component behavior, live props, documentation. |
| **Notion / Confluence** | Written rationale, context, and process docs. |
| **Jira / Linear** | Tickets, acceptance criteria, and tracking. |
| **Loom** | Walkthroughs for complex flows. |

---

## 8. The Handoff Process

1. **Designer prepares** the final file, organizes layers, and adds annotations.
2. **Design review** with engineers and product to clarify intent.
3. **Engineer picks up** the ticket and inspects specs.
4. **Questions are asked** in the design file or project tool.
5. **Developer builds** with reference to specs and components.
6. **Designer reviews** the build for fidelity and UX.
7. **Iterate** until the build matches intent.

---

## 9. Red Flags in Handoff

- Designs with no naming convention or layer organization.
- Missing responsive or mobile states.
- Hard-coded values instead of design tokens.
- No loading, error, or empty states.
- Vague microcopy or placeholder text.
- Ambiguous interactions with no behavior notes.
- No accessibility considerations.

---

## 10. Collaboration Tips

- Involve engineers early, not just at handoff.
- Use the same language: tokens, components, breakpoints.
- Annotate directly in the design file.
- Record short Loom videos for complex flows.
- Keep a changelog of design updates.
- Plan for design QA after build.

---

## 11. Checklist

- [ ] All screens and states are present.
- [ ] Responsive and mobile views are included.
- [ ] Design tokens are used for colors, spacing, and type.
- [ ] Components are mapped to the design system.
- [ ] Micro-interactions and transitions are documented.
- [ ] Loading, empty, and error states are designed.
- [ ] Accessibility notes are included.
- [ ] Assets are organized and exportable.
- [ ] Prototypes cover key user flows.
- [ ] Engineers have reviewed and asked questions.
- [ ] Design QA is planned before release.
