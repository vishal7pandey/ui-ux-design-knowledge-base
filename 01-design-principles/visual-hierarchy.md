# Visual Hierarchy

## What Is Visual Hierarchy?

Visual hierarchy is the arrangement of elements to guide the user's eye through the interface in order of importance. It answers: **"What should I look at first?"**

## Tools of Hierarchy

### 1. Size
Larger = more important. The biggest element on the screen gets attention first.

```
H1 (39px)  →  Most important — page title
H2 (25px)  →  Section title
H3 (20px)  →  Subsection
Body (16px)→  Content
```

### 2. Color & Contrast
High contrast draws the eye. Low contrast recedes.

- **Primary CTA:** High contrast against background (e.g., blue button on white).
- **Secondary CTA:** Lower contrast (e.g., outlined or gray button).
- **Tertiary actions:** Even lower (text link or ghost button).

### 3. Weight (Boldness)
Bold text stands out. Use sparingly for emphasis.

- **Bold:** Headlines, key numbers, button labels.
- **Medium:** Nav items, table headers, card titles.
- **Regular:** Body text, descriptions.

### 4. Position
- **Top-left** (in LTR languages): First thing read.
- **Center:** Focal point for hero sections.
- **Bottom-right:** Where the eye lands last — good for CTAs.

### 5. Whitespace
More whitespace around an element = more importance.

```
[Card with 48px padding]  →  feels premium, important
[Card with 8px padding]   →  feels dense, secondary
```

### 6. Color Saturation
Saturated colors pop. Desaturated colors blend in.

- Use saturated colors for CTAs and important highlights.
- Use desaturated/neutral colors for chrome and secondary content.

### 7. Texture & Depth
- **Shadows** elevate elements (modals, dropdowns, sticky headers).
- **Borders** define boundaries without elevation.
- **Flat** elements feel embedded in the surface.

### 8. Motion
Animated or moving elements capture attention. Use for:
- New content appearing (fade-in, slide-in).
- Important state changes.
- Onboarding highlights.

> **Warning:** Don't overuse motion — it becomes noise.

## Hierarchy in Practice

### Page-Level Hierarchy
```
1. Page title (H1)           ← What page am I on?
2. Primary CTA               ← What should I do?
3. Key content / data         ← What information do I need?
4. Secondary content          ← What else is available?
5. Navigation / footer        ← Where can I go?
```

### Card-Level Hierarchy
```
1. Card title (bold)          ← What is this?
2. Key metric / image          ← What's the highlight?
3. Description / metadata      ← More detail
4. Action button               ← What can I do?
```

### Form Hierarchy
```
1. Form heading               ← What am I filling out?
2. Section labels              ← How is it organized?
3. Input labels                ← What goes here?
4. Helper text                 ← How do I fill this correctly?
5. Submit button               ← How do I finish?
```

## The Squint Test

Squint at your design (or blur it). What stands out? That's what users will notice first. If the wrong thing stands out, adjust your hierarchy.

## F-Pattern & Z-Pattern

### F-Pattern (Content-Heavy)
Users scan in an F-shape: top bar, then down the left side, with horizontal scans.
- Put important content on the left.
- Use headings and bold text to create "scan stops."

### Z-Pattern (Minimal Content)
Users scan corner-to-corner in a Z-shape.
- Top-left: Logo
- Top-right: Navigation
- Bottom-left: Supporting info
- Bottom-right: CTA

## Common Hierarchy Mistakes

| Mistake | Fix |
|---|---|
| Everything is the same size | Use a clear type scale |
| Too many bold elements | Bold only the most important items |
| Multiple competing CTAs | One primary CTA per view |
| No whitespace between sections | Add 32px+ between major sections |
| All buttons look the same | Differentiate primary, secondary, tertiary |
| Low contrast on important elements | Increase contrast for key actions |
| Decorative images compete with content | Reduce their size or saturation |

## Hierarchy Checklist

- [ ] Can I identify the #1 most important element in 1 second?
- [ ] Is there only one primary CTA per screen/section?
- [ ] Does the type scale have clear jumps between levels?
- [ ] Is whitespace used to separate and group content?
- [ ] Does the squint test reveal the right priorities?
- [ ] Are secondary actions visually de-emphasized?
