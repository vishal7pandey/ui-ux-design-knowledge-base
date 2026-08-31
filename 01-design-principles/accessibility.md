# Accessibility (a11y) Guidelines

## Why Accessibility Matters

- **1 billion+ people** worldwide have some form of disability.
- **Legal requirement** in many countries (ADA, WCAG, Section 508, EN 301 549).
- **Better UX for everyone** — captions help in noisy environments, high contrast helps in bright sunlight.
- **SEO benefits** — accessible sites are better structured for search engines.

## WCAG 2.2 Quick Reference

### POUR Principles
1. **Perceivable** — Users can perceive all content (see, hear).
2. **Operable** — Users can interact with all elements (keyboard, touch, voice).
3. **Understandable** — Content and controls are clear.
4. **Robust** — Works with assistive technologies.

### Conformance Levels
- **Level A** (minimum) — Must support basic accessibility.
- **Level AA** (target) — Should be your baseline. Most legal requirements reference this.
- **Level AAA** (gold standard) — Nice to have for critical content.

## Color & Contrast

### Minimum Contrast Ratios
| Element | AA | AAA |
|---|---|---|
| Normal text (<18pt) | 4.5:1 | 7:1 |
| Large text (≥18pt or ≥14pt bold) | 3:1 | 4.5:1 |
| UI components & graphical objects | 3:1 | — |
| Non-essential decoration | No requirement | — |

### Rules
- **Never use color alone** to convey meaning. Pair with text, icons, or patterns.
  - Bad: Red text for errors only.
  - Good: Red text + warning icon + "Error:" label.
- **Provide focus indicators** with at least 3:1 contrast against adjacent colors.
- **Test with a color blindness simulator** — deuteranopia (red-green) is most common.

### Tools
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [Color Oracle](https://colororacle.org/) — color blindness simulator
- [Stark](https://www.getstark.co/) — Figma/Sketch plugin

## Keyboard Accessibility

### Requirements
- All interactive elements must be reachable via `Tab` key.
- Logical tab order (follows visual order, usually top-to-bottom, left-to-right).
- Visible focus indicator (never remove `:focus` outline without replacement).
- No keyboard traps (user can always `Esc` out of modals, overlays).

### Key Bindings
| Key | Action |
|---|---|
| `Tab` | Move to next focusable element |
| `Shift + Tab` | Move to previous focusable element |
| `Enter` | Activate button or link |
| `Space` | Activate button, toggle checkbox |
| `Esc` | Close modal, dropdown, popover |
| `Arrow keys` | Navigate within components (tabs, menus, sliders) |
| `Home / End` | Jump to first/last item in a list |

### Focus Order
```
1. Skip to content link (if present)
2. Logo / home
3. Primary navigation
4. Main content (top to bottom)
5. Footer
```

### Skip Links
Provide a "Skip to main content" link as the first focusable element:
```html
<a href="#main" class="skip-link">Skip to main content</a>
```

## Screen Reader Support

### Semantic HTML
Use the right HTML element for the job — screen readers understand semantics.

| Purpose | Use | Don't Use |
|---|---|---|
| Navigation | `<nav>` | `<div class="nav">` |
| Main content | `<main>` | `<div id="content">` |
| Section | `<section>` | `<div class="section">` |
| Article | `<article>` | `<div class="post">` |
| Sidebar | `<aside>` | `<div class="sidebar">` |
| Header | `<header>` | `<div class="header">` |
| Footer | `<footer>` | `<div class="footer">` |
| Button | `<button>` | `<div onclick="...">` |
| Link | `<a href>` | `<span onclick="...">` |
| Form | `<form>` | `<div class="form">` |
| Input label | `<label>` | `<span class="label">` |

### ARIA (Accessible Rich Internet Applications)

**Rule #1: No ARIA is better than bad ARIA.** Use semantic HTML first.

#### When to Use ARIA
- Dynamic content (live regions, AJAX updates).
- Custom widgets (tabs, accordions, modals) — use ARIA roles/states.
- Adding labels to icon-only buttons.

#### Common ARIA Attributes
```html
<!-- Label for icon-only button -->
<button aria-label="Close dialog">×</button>

<!-- Describe relationship -->
<input aria-describedby="email-help" />
<small id="email-help">We'll never share your email.</small>

<!-- Current page in navigation -->
<a href="/home" aria-current="page">Home</a>

<!-- Expanded state -->
<button aria-expanded="false" aria-controls="menu">Menu</button>

<!-- Live region for dynamic updates -->
<div aria-live="polite">Status updates appear here</div>
<div aria-live="assertive">Critical errors appear here</div>
```

### Alt Text
```html
<!-- Informative image -->
<img src="chart.png" alt="Sales increased 45% from Q1 to Q2 2024" />

<!-- Decorative image -->
<img src="divider.png" alt="" />

<!-- Functional image (link) -->
<a href="/home"><img src="logo.png" alt="Go to homepage" /></a>
```

**Alt text rules:**
- Describe the **purpose**, not the appearance.
- Keep it under 125 characters.
- Don't start with "Image of" or "Picture of."
- Use `alt=""` for decorative images (screen readers skip them).

## Forms

### Labels
- Every input has a visible `<label>` associated via `for`/`id`.
- Placeholder text is NOT a label.
- Group related fields with `<fieldset>` and `<legend>`.

```html
<label for="email">Email address</label>
<input type="email" id="email" required />

<fieldset>
  <legend>Shipping method</legend>
  <label><input type="radio" name="shipping" value="standard" /> Standard</label>
  <label><input type="radio" name="shipping" value="express" /> Express</label>
</fieldset>
```

### Error Identification
- Errors are announced to screen readers (`aria-live` or `role="alert"`).
- Error messages are specific and actionable.
- Error fields are associated with their messages via `aria-describedby`.
- Don't clear the form on error — preserve user input.

### Required Fields
- Mark with both visual indicator (*) and `aria-required="true"` or HTML5 `required`.
- Explain what the asterisk means at the top of the form.

## Media Accessibility

### Images
- Informative images: descriptive alt text.
- Decorative images: empty alt (`alt=""`).
- Complex images (charts, diagrams): alt text + longer description nearby.

### Video
- **Captions** for all spoken content.
- **Audio descriptions** for important visual information.
- Transcript available as alternative.
- Don't autoplay with sound.

### Audio
- Transcript available.
- Provide pause/stop controls.

## Motion & Animation

- Respect `prefers-reduced-motion` media query.
- Provide option to disable non-essential animations.
- No content that flashes more than 3 times per second (seizure risk).

```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

## Touch & Motor Accessibility

- **Minimum touch target:** 44×44 CSS pixels (WCAG 2.5.5).
- **Spacing between targets:** At least 8px between adjacent interactive elements.
- **No time limits** on interactions, or provide extension options.
- **Drag-and-drop** must have a keyboard-accessible alternative.

## Cognitive Accessibility

- **Plain language** — aim for 8th-grade reading level for general audiences.
- **Consistent navigation** — same patterns across pages.
- **Error prevention** — confirmations for destructive actions.
- **Clear instructions** — tell users what's expected.
- **Predictable behavior** — no surprising page changes or redirects.

## Testing

### Automated Testing
- **axe DevTools** — browser extension, scans for common issues.
- **Lighthouse** — Chrome DevTools, includes accessibility audit.
- **WAVE** — browser extension for visual accessibility feedback.
- **Pa11y** — CLI tool for automated testing in CI.

### Manual Testing
- **Keyboard-only navigation** — unplug your mouse, can you use the site?
- **Screen reader testing** — NVDA (Windows), VoiceOver (Mac/iOS), TalkBack (Android).
- **Zoom to 200%** — does the layout still work?
- **High contrast mode** — does the UI still function?
- **Color blindness simulator** — test with Color Oracle or browser DevTools.

### Testing Checklist
- [ ] All interactive elements keyboard accessible
- [ ] Visible focus indicator on all focusable elements
- [ ] Logical tab order
- [ ] Screen reader announces all content correctly
- [ ] All images have appropriate alt text
- [ ] All forms have labels and error messages
- [ ] Color contrast meets AA minimum
- [ ] No information conveyed by color alone
- [ ] Page works at 200% zoom
- [ ] Page works with `prefers-reduced-motion`
- [ ] No flashing content > 3 times/second
- [ ] Skip link present and functional
