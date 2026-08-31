# Component Library Architecture

## What Is a Component Library?

A component library is a collection of reusable, pre-built UI components that implement your design system. It's the code-level realization of your design tokens and component patterns.

## Architecture Layers

```
┌─────────────────────────────────────────────┐
│  Application                                │  ← Your product
├─────────────────────────────────────────────┤
│  Composition / Patterns                     │  ← Page templates, layouts
├─────────────────────────────────────────────┤
│  Components                                 │  ← Buttons, inputs, cards
├─────────────────────────────────────────────┤
│  Primitives                                 │  ← Box, Text, Icon, Stack
├─────────────────────────────────────────────┤
│  Design Tokens                              │  ← Colors, spacing, typography
├─────────────────────────────────────────────┤
│  Theme                                      │  ← Token values (light/dark)
└─────────────────────────────────────────────┘
```

## Component Categories

### 1. Primitives
The lowest-level building blocks. Usually not used directly by product teams.

| Primitive | Purpose |
|---|---|
| Box | Div with design token props (padding, bg, radius) |
| Text | Typography with token-based sizing |
| Stack | Vertical/horizontal layout with gap |
| Icon | SVG icon with size and color props |
| Divider | Horizontal/vertical separator |
| VisuallyHidden | Accessible hidden text |

### 2. Components
Self-contained UI elements with clear APIs.

| Component | Variants |
|---|---|
| Button | Primary, secondary, ghost, icon, sizes |
| Input | Text, email, password, search, error states |
| Select | Single, multi, searchable, combobox |
| Checkbox | Default, indeterminate, disabled |
| Radio | Default, disabled |
| Toggle | On/off, disabled |
| Card | Basic, interactive, with media |
| Badge | Default, success, warning, error |
| Avatar | Image, initials, fallback, sizes |
| Tooltip | Top, bottom, left, right |
| Modal | Dialog, confirmation, form |
| Toast | Success, error, warning, info |
| Tabs | Underline, filled, pill |
| Table | Basic, sortable, selectable, paginated |
| Pagination | Numbers, load more |

### 3. Patterns / Compositions
Multi-component combinations that solve common UX patterns.

| Pattern | Components Used |
|---|---|
| Form Field | Label + Input + Helper text + Error |
| Search Bar | Input + Button + Clear icon |
| Data Table | Table + Pagination + Filters + Empty state |
| Card Grid | Card + Grid layout + Loading skeletons |
| App Shell | Sidebar + Top bar + Content area |
| Auth Form | Form Field + Button + Link + Validation |

## Component API Design

### Props Convention

```tsx
// Button component example
interface ButtonProps {
  // Variant
  variant?: 'primary' | 'secondary' | 'ghost' | 'danger';
  size?: 'sm' | 'md' | 'lg';

  // State
  loading?: boolean;
  disabled?: boolean;
  fullWidth?: boolean;

  // Content
  children: React.ReactNode;
  leftIcon?: React.ReactNode;
  rightIcon?: React.ReactNode;

  // Behavior
  onClick?: (e: MouseEvent) => void;
  type?: 'button' | 'submit' | 'reset';

  // Accessibility
  ariaLabel?: string;

  // Escape hatch
  className?: string;
  style?: CSSProperties;
}
```

### API Principles
1. **Sensible defaults:** `<Button>Save</Button>` works out of the box
2. **Composable:** Components can be combined without conflict
3. **Overridable:** Provide escape hatches (`className`, `style`) for edge cases
4. **Accessible:** Include ARIA props, keyboard support by default
5. **Typed:** Full TypeScript types for all props
6. **Documented:** Every prop has a description and example

## Component States

Every interactive component should handle:

| State | CSS | Description |
|---|---|---|
| Default | `:default` | Resting state |
| Hover | `:hover` | Mouse over (desktop) |
| Focus | `:focus-visible` | Keyboard focus |
| Active | `:active` | Being pressed |
| Disabled | `:disabled` | Not interactive |
| Loading | `.is-loading` | Async operation |
| Error | `.has-error` | Validation failed |
| Selected | `.is-selected` | Chosen from a list |
| Visited | `:visited` | (Links only) |

## Component Documentation

### Each component should document:

1. **Overview** — what it does, when to use it
2. **Props table** — name, type, default, description
3. **Examples** — common use cases with code
4. **Variants** — all visual variants
5. **States** — all interactive states
6. **Accessibility** — keyboard support, ARIA attributes
7. **Do's and don'ts** — usage guidelines

### Example Documentation Structure
```
Button
├── Overview
├── Imports
├── Usage (basic example)
├── Variants
│   ├── Primary
│   ├── Secondary
│   ├── Ghost
│   └── Danger
├── Sizes
├── With Icons
├── Loading State
├── Disabled State
├── Full Width
├── Props Reference
├── Accessibility
└── Do's and Don'ts
```

## Versioning

### Semantic Versioning
- **Major (x.0.0):** Breaking changes (API changes, removed props)
- **Minor (0.x.0):** New features (new component, new prop, new variant)
- **Patch (0.0.x):** Bug fixes, style tweaks, accessibility improvements

### Migration Strategy
- Deprecate before removing (warn in console)
- Provide codemods for common migrations
- Document upgrade guides for each major version
- Maintain a changelog

## Testing

### Visual Testing
- Storybook + Chromatic for visual regression
- Test all variants and states
- Test in light and dark mode

### Unit Testing
- Test component logic (state changes, event handlers)
- Test prop combinations
- Test accessibility attributes

### Accessibility Testing
- jest-axe for automated a11y testing
- Keyboard navigation tests
- Screen reader testing

## Organization

### Monorepo Structure
```
design-system/
├── packages/
│   ├── tokens/          ← Design tokens
│   ├── primitives/      ← Low-level components
│   ├── components/      ← UI components
│   ├── icons/           ← Icon library
│   ├── theme/           ← Theme provider + presets
│   └── utils/           ← Shared utilities
├── apps/
│   ├── docs/            ← Documentation site
│   └── playground/      ← Component playground
├── package.json
└── turbo.json
```

### Package Publishing
- Publish each package independently
- Use a build tool (tsup, Rollup, Vite) for distribution
- Ship ESM + CJS + types
- Tree-shakeable imports

## Adoption Strategy

### 1. Start with Tokens
- Adopt design tokens first (CSS variables)
- This gives immediate consistency wins

### 2. Introduce Primitives
- Replace raw HTML with primitives (Box, Text, Stack)
- Gradual migration, no breaking changes

### 3. Roll Out Components
- One component at a time
- Start with highest-usage components (Button, Input, Card)
- Provide migration guides for each

### 4. Enforce Usage
- ESLint rules to ban raw HTML or hardcoded values
- Code review checklist
- Design system office hours for support

## Maintenance

### Responsibilities
| Role | Responsibilities |
|---|---|
| Design system team | Build, maintain, document, version |
| Product teams | Use, report bugs, request features |
| Designers | Define specs, review implementations |
| Leadership | Prioritize, resource, advocate |

### Governance
- Contribution model: who can add/modify components?
- Review process: design + code review for all changes
- RFC process: for significant additions or changes
- Regular audits: check for consistency, accessibility, performance

---

## Design-System Maturity: A 6-Dimension Framework

Linear "maturity ladder" models (build → adopt → scale → govern) are appealing but misleading — design systems don't progress in a straight line. Organizations restructure, mergers introduce conflicting systems, and budgets shift, causing systems to **regress** in ways builders can't control. A 10-person startup and a 10,000-person enterprise can both have a "mature" system — maturity is contextual to scale, not a universal ladder.

Instead, assess maturity as a **multidimensional profile** across 6 independent dimensions. Plot scores on a radar chart; the resulting shape is your system's health snapshot.

### The 6 Dimensions

| Dimension | What It Measures |
|---|---|
| **Organizational Alignment** | Leadership sponsorship, funding stability, strategic positioning (core infrastructure vs. optional service), cross-functional buy-in |
| **Team Effectiveness** | Capacity/sustainability, cross-functional expertise (design + eng + content + a11y + PM), collaboration quality, staff wellbeing |
| **Infrastructure Robustness** | Component coverage & cross-platform consistency, token/foundation structure, documentation completeness, tooling quality, accessibility built-in |
| **Governance** | Contribution models, deviation/exception handling, flexibility vs. brand-consistency balance, versioning/release strategy, prioritization framework |
| **Support** | Onboarding, responsive help channels, communication (changelogs, roadmaps), champions programs, feedback loops |
| **Adoption** | **Usage** (do teams have access & use it?), **Conformance** (do they apply it correctly, or work around it?), **Trust** (do teams believe it's reliable and will evolve to meet their needs?) |

> Of everything determining whether a system endures, **organizational alignment is the most foundational.** A system can survive incomplete docs or loose governance for a while — it can't survive an organization that's decided it isn't worth investing in.

### Running a Maturity Assessment

**Step 1 — Choose evaluators (4–8 people):**
- Design-system team members across disciplines
- Product-team representatives who use the system daily
- Key stakeholders/sponsors with visibility into organizational alignment

**Step 2 — Score independently (1–5 scale) on each dimension:**

| Score | Level | Meaning |
|---|---|---|
| 1 | Absent | No intentional structure; ad hoc or nonexistent effort |
| 2 | Emerging | Some awareness/early effort, but inconsistent and informal |
| 3 | Functional | A defined approach handles routine needs but is fragile under scale/change |
| 4 | Strong | Consistent, clearly owned, reliably applied practices |
| 5 | Exceptional | Mature, continuously improving, resilient through major org change |

**Step 3 — Triangulate and align:** Where scores converge, note the consensus and move on. Where scores diverge significantly (e.g., the design-system team rates Support a 4, but product teams rate it a 2), use the gap as a discussion prompt — it often reveals a mismatch between intended investment and perceived value (e.g., poor discoverability of existing resources).

**Step 4 — Plot the shape** on a hexagonal radar chart and read the pattern:

| Pattern | What It Signals |
|---|---|
| **Shape area** | General maturity — but a smaller shape isn't inherently bad; it may reflect appropriate scale for org size/stage |
| **Symmetry** | Balanced capabilities are more stable than large-but-uneven ones. A system scoring 5 on Support but 2 on Team Effectiveness can't sustain that service level |
| **Valleys** | A single low dimension often creates a structural bottleneck that undermines otherwise-strong areas. Fix the weakest link first |
| **Spikes** | High outliers may reflect intentional strategic investment — or compensation for a gap elsewhere (e.g., heavy Infrastructure investment masking weak Governance/Support) |

**Step 5 — Benchmark regularly:** Reassess quarterly or after major org shifts (reorg, big release, budget change). Keep a baseline and compare longitudinally to see whether the system is strengthening, fragmenting, or adapting.

### Why the Assessment Itself Matters
Beyond the scores, the shared discussion process is often more valuable than the resulting numbers. Involving system users and sponsors in scoring builds ownership (the **IKEA effect** — people who help define a system's strengths/gaps become more invested in its success and more likely to adopt and defend it).

**Bottom line:** design-system maturity isn't a fixed state or a single metric to chase. It's a dynamic balance across dimensions — components are the most visible artifact, but rarely what determines whether the system actually succeeds.
