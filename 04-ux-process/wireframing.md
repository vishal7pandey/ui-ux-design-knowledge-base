# Wireframing

## What Is a Wireframe?

A wireframe is a low-fidelity visual representation of a page's structure, focusing on layout, content placement, and functionality — without visual design (colors, images, typography styling).

## Purpose

- **Communicate structure** before investing in visual design
- **Validate layout** with stakeholders and users
- **Identify problems early** when they're cheap to fix
- **Align the team** on what goes where and why
- **Plan content** and information hierarchy

## Fidelity Levels

### Low-Fidelity (Sketch / Paper)
```
┌─────────────────────────┐
│  [Logo]    [Nav items]   │
├─────────────────────────┤
│                         │
│    [   Hero Title   ]   │
│    [   Subtitle     ]   │
│    [   CTA Button   ]   │
│                         │
├─────────────────────────┤
│  [Card]  [Card]  [Card] │
├─────────────────────────┤
│  [Footer links]          │
└─────────────────────────┘
```
- **Speed:** Minutes per screen
- **Purpose:** Explore layouts, get quick feedback
- **Tools:** Paper, whiteboard, Excalidraw, Balsamiq

### Medium-Fidelity (Graybox)
```
┌─────────────────────────────────┐
│  ▓▓▓▓        ▓▓ ▓▓ ▓▓    [🔍]   │
├─────────────────────────────────┤
│                                 │
│    ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓         │
│    ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓           │
│         [ ▓▓▓▓▓▓▓▓▓ ]          │
│                                 │
├─────────────────────────────────┤
│  ┌─────┐  ┌─────┐  ┌─────┐     │
│  │ ▓▓▓ │  │ ▓▓▓ │  │ ▓▓▓ │     │
│  │ ▓▓▓ │  │ ▓▓▓ │  │ ▓▓▓ │     │
│  └─────┘  └─────┘  └─────┘     │
├─────────────────────────────────┤
│  ▓▓▓ ▓▓▓ ▓▓▓ ▓▓▓ ▓▓▓           │
└─────────────────────────────────┘
```
- **Speed:** 30-60 minutes per screen
- **Purpose:** Detailed layout, content sizing, component placement
- **Tools:** Figma, Sketch, Adobe XD

### High-Fidelity (Detailed Wireframe)
- Includes real content (or close to it)
- Shows exact spacing, component types
- May include annotations
- **Purpose:** Final layout before visual design
- **Tools:** Figma, Sketch, Adobe XD

## Wireframe Elements

### Placeholder Conventions
| Element | Representation |
|---|---|
| Text | Lines (▓▓▓▓▓) or lorem ipsum |
| Images | Boxes with X or mountain icon |
| Buttons | Rounded rectangles with label |
| Input fields | Rectangles with label |
| Video | Rectangle with play icon |
| Icons | Simple geometric shapes |
| Charts | Bar/line placeholders |

## Wireframing Process

### 1. Define the Goal
- What is this page/screen for?
- What should the user do here?
- What content is needed?

### 2. Start with Content
- List all content elements needed
- Prioritize: what's most important?
- Group related content

### 3. Sketch Multiple Layouts
- Try 2-3 different layouts
- Don't refine — just explore
- Get feedback on rough directions

### 4. Refine the Best Direction
- Choose the strongest layout
- Add detail: exact components, spacing
- Consider responsive behavior

### 5. Annotate
- Add notes explaining interactions
- Mark hover states, click behaviors
- Note any special requirements

## Key Principles

### Content First
Design the content structure before the visual container. What information does the user need, and in what order?

### Mobile First
Start with the smallest screen. It forces you to prioritize. Then scale up to tablet and desktop.

### Progressive Disclosure
Don't show everything at once. Start with the essentials, reveal details on demand.

### One Primary Action
Each screen should have one clear primary action. Wireframes should make this obvious through size and position.

### Consistent Patterns
Use the same layout patterns across similar screens. Users learn once, apply everywhere.

## What to Include in Wireframes

### Always Include
- Navigation structure
- Content areas (with relative sizes)
- Primary and secondary actions
- Form fields (if applicable)
- Key interactive elements
- Responsive breakpoints (or separate wireframes per breakpoint)

### Don't Include (Yet)
- Colors
- Real images
- Typography styling (font choices, weights)
- Detailed visual design
- Animations

## Annotations

### What to Annotate
- **Interactions:** What happens when you click X?
- **States:** Default, hover, active, error, empty
- **Content rules:** Character limits, dynamic content
- **Behavior:** Sticky elements, scroll behavior
- **Responsive:** How layout changes across breakpoints
- **Edge cases:** What if there are 0 items? 1000 items?

### Annotation Format
```
  ┌───────────────────┐
  │  [Search input]    │ ← A1: Auto-suggest after 3 chars
  └───────────────────┘
                       ← A2: Results dropdown, max 10 items

  ┌───────────────────┐
  │  [Product card]    │ ← B1: Entire card clickable
  └───────────────────┘   ← B2: Opens product detail page
```

## Wireframe Review Checklist

- [ ] Does the layout serve the primary goal?
- [ ] Is the most important content prominent?
- [ ] Is there one clear primary action?
- [ ] Is the navigation logical?
- [ ] Are related items grouped?
- [ ] Is the content hierarchy clear?
- [ ] Does it work on mobile?
- [ ] Are edge cases considered (empty, error, loading)?
- [ ] Are interactions annotated?
- [ ] Can stakeholders understand it without explanation?

## Tools

| Tool | Type | Best For |
|---|---|---|
| **Paper & pen** | Analog | Quick ideation, exploration |
| **Excalidraw** | Digital (free) | Hand-drawn style, collaboration |
| **Balsamiq** | Digital (paid) | Classic wireframing, low-fi |
| **Figma** | Digital (freemium) | All fidelity levels, collaboration |
| **Sketch** | Digital (paid) | Mac users, all fidelity levels |
| **Whimsical** | Digital (freemium) | Quick wireframes, flowcharts |
| **Adobe XD** | Digital (paid) | Adobe ecosystem users |

## Tips

1. **Don't make wireframes pretty** — they should look unfinished so feedback focuses on structure, not visuals
2. **Wireframe the happy path AND edge cases** — empty states, error states, loading states
3. **Use real content when possible** — "Lorem ipsum" hides content sizing issues
4. **Wireframe all screens in a flow** — don't just do the main page, do the full journey
5. **Get feedback early and often** — wireframes are cheap to change, high-fidelity designs are not
6. **Name your wireframes** — "Homepage v3" not "Untitled-3"
