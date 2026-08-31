# Prototyping

## What Is a Prototype?

A prototype is an interactive simulation of your product. It goes beyond static wireframes by allowing users to click through flows, experience transitions, and interact with the design as they would the real product.

## Prototype Fidelity Levels

### Low-Fidelity (Clickable Wireframes)
- Wireframe screens linked together
- Basic click navigation
- No transitions or animations
- **Purpose:** Test navigation and flow

### Medium-Fidelity
- Styled components (real colors, typography)
- Basic transitions between screens
- Some interactive elements (dropdowns, tabs)
- **Purpose:** Test usability and gather detailed feedback

### High-Fidelity
- Pixel-perfect visual design
- Real interactions and animations
- Real or realistic content
- May include micro-interactions
- **Purpose:** Final validation before development, stakeholder approval

### Code Prototype
- Built in actual code (HTML/CSS/JS or React)
- Real interactions and data
- **Purpose:** Test technical feasibility, performance, real user testing

## When to Prototype

| Stage | Prototype Type | Purpose |
|---|---|---|
| **Ideation** | Paper prototype | Test concepts quickly |
| **Wireframing** | Clickable wireframes | Validate flows and navigation |
| **Design** | Medium-fi prototype | Test usability, gather feedback |
| **Pre-development** | High-fi prototype | Final validation, stakeholder sign-off |
| **Development** | Code prototype | Test technical feasibility |

## What to Prototype

### Always Prototype
- New user flows (onboarding, checkout, registration)
- Complex interactions (drag-and-drop, multi-step forms)
- Navigation patterns (new menu structures, tab systems)
- Critical paths (anything that directly impacts revenue or retention)

### Don't Need to Prototype
- Simple static pages (about, contact, legal)
- Pages using existing patterns
- Minor updates to existing screens
- Backend/admin tools with standard CRUD

## Prototyping Process

### 1. Define the Scope
- What flow(s) will the prototype cover?
- What screens are needed?
- What interactions are essential vs. nice-to-have?

### 2. Map the Flow
```
Login → Dashboard → Project List → New Project → Settings
```
- List all screens in the flow
- Identify decision points (branches)
- Note what happens at each step

### 3. Design the Screens
- Design each screen at the appropriate fidelity
- Ensure visual consistency across screens
- Include all states (default, hover, error, empty, loading)

### 4. Connect the Screens
- Link interactive elements to target screens
- Add transitions (slide, fade, push)
- Set up overlays (modals, dropdowns, tooltips)
- Create scroll behavior (scroll to position, sticky elements)

### 5. Add Interactions
- Form inputs that accept text
- Toggles and checkboxes that change state
- Conditional logic (show X if Y is selected)
- Smart animate (auto-animate between component states)

### 6. Test
- Click through the prototype yourself first
- Fix any broken links or dead ends
- Test with users (see usability-testing.md)
- Iterate based on feedback

## Prototyping in Figma

### Key Features
| Feature | What It Does |
|---|---|
| **Connections** | Link elements between frames |
| **Interactions** | Click, hover, drag, key press triggers |
| **Transitions** | Slide, fade, push, move, dissolve |
| **Smart Animate** | Auto-animate between matching layers |
| **Overlays** | Modals, dropdowns, tooltips |
| **Scroll Behavior** | Fixed/sticky elements, scroll-to |
| **Components** | Reusable elements with variants |
| **Conditional Logic** | Show/hide based on variables (Figma variables) |

### Figma Prototype Tips
- Use **Components** for consistency across screens
- Use **Variants** for component states (default, hover, active, disabled)
- Use **Smart Animate** for smooth state transitions
- Group screens by flow in your file
- Name layers clearly — it helps when setting up interactions
- Use **Prototype settings** to set the right device frame

## Interaction Patterns to Prototype

### Navigation
- Tab switching (with content transition)
- Sidebar expand/collapse
- Breadcrumb navigation
- Back button behavior

### Forms
- Input focus states
- Validation on blur
- Error messages appearing
- Form submission (loading → success/error)
- Multi-step form progression

### Data
- Table sorting (column header click)
- Filter application (results update)
- Pagination (page transition)
- Search (typing → results appear)

### Feedback
- Toast notifications appearing/disappearing
- Modal opening/closing
- Loading states (skeleton → content)
- Empty states (no data → first action)

### Drag & Drop
- Element pickup (shadow, scale)
- Drop target highlighting
- Reordering (items shift)
- Drop confirmation

## Prototype Testing

### Preparation
1. **Write a task script** — specific tasks for users to complete
2. **Set up recording** — screen + audio capture
3. **Test the prototype yourself** — fix broken links
4. **Prepare a quiet space** — or set up remote testing

### During the Test
- **Don't explain the interface** — let users figure it out
- **Ask them to think aloud** — "Tell me what you're looking for"
- **Don't help them** — note where they struggle (that's the insight)
- **Ask follow-up questions** — "What did you expect to happen?"

### Common Issues to Watch For
- Users getting lost in navigation
- Not noticing the primary CTA
- Confusing labels or icons
- Unexpected interactions
- Dead ends (no way back)

## Handoff from Prototype

### For Developers
- Provide the prototype link
- Export assets (icons, images)
- Document interactions that aren't obvious
- Provide design specs (spacing, colors, typography)
- Note any animations with timing/easing details

### For Stakeholders
- Walk through the prototype in a meeting
- Explain key decisions and trade-offs
- Show how user feedback was incorporated
- Get explicit sign-off before development

## Tools

| Tool | Type | Best For |
|---|---|---|
| **Figma** | Design + prototype | Industry standard, collaboration |
| **Framer** | Design + prototype | Advanced interactions, code components |
| **Protopie** | Prototype only | Complex interactions, sensor data |
| **Principle** | Prototype only | Animations (Mac only) |
| **Adobe XD** | Design + prototype | Adobe ecosystem |
| **InVision** | Prototype only | Linking static screens |
| **Marvel** | Prototype only | Simple, quick prototypes |
| **Code (HTML/CSS/JS)** | Code prototype | Real interactions, technical testing |

## Tips

1. **Prototype the critical path first** — don't prototype everything at once
2. **Fake data is fine** — use realistic but fake data, don't connect to real APIs yet
3. **Don't over-invest in prototypes** — they're disposable, not the final product
4. **Test with 5 users** — you'll find 85% of usability issues with just 5 participants
5. **Iterate quickly** — fix issues and re-test the same day if possible
6. **Keep old versions** — you might want to revert or compare
