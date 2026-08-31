# Accessibility Checklist

A thorough accessibility checklist based on WCAG 2.2 AA standards.

## Color & Contrast

- [ ] Body text contrast ratio is at least 4.5:1
- [ ] Large text (18pt+ or 14pt+ bold) contrast ratio is at least 3:1
- [ ] UI components and graphical elements have 3:1 contrast against adjacent colors
- [ ] Focus indicators have 3:1 contrast against adjacent colors
- [ ] Color is not the sole means of conveying information
- [ ] Links are distinguishable (not by color alone — underline or icon)
- [ ] Error/success states use icons + text, not just color
- [ ] Tested with a color blindness simulator

## Keyboard Accessibility

- [ ] All interactive elements are reachable via Tab key
- [ ] Tab order is logical (follows visual order)
- [ ] Focus is visible on all focusable elements
- [ ] Focus is never removed without a replacement indicator
- [ ] No keyboard traps (user can always Tab out or press Esc)
- [ ] Skip-to-content link is present and functional
- [ ] Custom widgets support arrow key navigation
- [ ] Enter activates buttons and links
- [ ] Space activates buttons and toggles checkboxes
- [ ] Esc closes modals, dropdowns, and overlays

## Screen Reader Support

- [ ] Semantic HTML used (`<nav>`, `<main>`, `<header>`, `<footer>`, `<button>`, `<a>`)
- [ ] Page has a descriptive `<title>`
- [ ] Headings are properly nested (h1 → h2 → h3, no skipped levels)
- [ ] All images have appropriate `alt` text
- [ ] Decorative images have empty `alt=""`
- [ ] Icon-only buttons have `aria-label`
- [ ] Form inputs have associated `<label>` elements
- [ ] Error messages are associated with inputs (`aria-describedby`)
- [ ] Dynamic content updates use `aria-live` regions
- [ ] ARIA is used only when semantic HTML is insufficient
- [ ] `role="dialog"` and `aria-modal="true"` on modals
- [ ] `aria-current="page"` on active navigation items

## Forms

- [ ] Every input has a visible `<label>` (placeholder is not a label)
- [ ] Required fields are marked visually and with `aria-required` or `required`
- [ ] Error messages are specific and actionable
- [ ] Errors are announced to screen readers (`role="alert"` or `aria-live`)
- [ ] Form validation doesn't clear user input on error
- [ ] Grouped form fields use `<fieldset>` and `<legend>`
- [ ] Autocomplete attributes are set for common fields
- [ ] Instructions are provided before the form, not after
- [ ] Submit button has a descriptive label

## Media

- [ ] Videos have synchronized captions
- [ ] Videos have audio descriptions for important visual info
- [ ] Audio content has a transcript
- [ ] No media autoplays with sound
- [ ] Media controls are keyboard accessible
- [ ] No content flashes more than 3 times per second

## Structure & Navigation

- [ ] HTML has a logical document structure
- [ ] `<main>` element wraps primary content
- [ ] Navigation is in a `<nav>` element
- [ ] Multiple ways to find pages (nav, search, sitemap)
- [ ] Breadcrumbs are available for deep hierarchies
- [ ] Consistent navigation across pages
- [ ] Consistent page structure across similar pages

## Touch & Motor

- [ ] Touch targets are minimum 44×44 CSS pixels
- [ ] Adequate spacing between adjacent touch targets (8px+)
- [ ] No time limits on interactions (or provide extension)
- [ ] Drag-and-drop has a keyboard-accessible alternative
- [ ] No reliance on hover-only interactions (touch alternative exists)

## Cognitive

- [ ] Plain language used (target 8th-grade reading level for general audience)
- [ ] Consistent navigation and layout across pages
- [ ] Error prevention for destructive actions (confirmations)
- [ ] Clear instructions provided for tasks
- [ ] Input purpose is clear (labels, helper text)
- [ ] No unexpected page changes or redirects
- [ ] Session timeouts have warning and extension option

## Responsive & Zoom

- [ ] Page is usable at 200% zoom
- [ ] Page is usable at 400% zoom (for low vision users)
- [ ] Text reflows without horizontal scroll at 320px width
- [ ] Content doesn't overlap or get cut off when zoomed
- [ ] Responsive design doesn't rely on hover-only states

## Motion & Animation

- [ ] `prefers-reduced-motion` media query is respected
- [ ] Non-essential animations can be disabled
- [ ] No parallax or auto-moving content that can't be paused
- [ ] No content that flashes more than 3 times per second
- [ ] Auto-playing carousels can be paused

## Testing

### Automated Testing
- [ ] axe DevTools scan passes (0 violations)
- [ ] Lighthouse accessibility audit scores 90+
- [ ] WAVE shows no errors
- [ ] HTML validates (W3C validator)

### Manual Testing
- [ ] Keyboard-only test completed (unplug mouse)
- [ ] Screen reader test completed (NVDA, VoiceOver, or TalkBack)
- [ ] 200% zoom test completed
- [ ] High contrast mode test completed
- [ ] Color blindness simulation test completed
- [ ] Mobile screen reader test (VoiceOver iOS or TalkBack Android)

### Browser Testing
- [ ] Tested in Chrome
- [ ] Tested in Firefox
- [ ] Tested in Safari
- [ ] Tested in Edge
- [ ] Tested on iOS (Safari)
- [ ] Tested on Android (Chrome)

## Documents & Downloads

- [ ] PDFs are tagged and accessible
- [ ] Documents have proper heading structure
- [ ] Document images have alt text
- [ ] Document reading order is correct
- [ ] Document language is set

## Common ARIA Patterns

### Accordion
```html
<button aria-expanded="true" aria-controls="panel1">Section 1</button>
<div id="panel1" role="region" aria-labelledby="heading1">Content</div>
```

### Tab Interface
```html
<div role="tablist">
  <button role="tab" aria-selected="true" aria-controls="panel1">Tab 1</button>
  <button role="tab" aria-selected="false" aria-controls="panel2">Tab 2</button>
</div>
<div role="tabpanel" id="panel1">Content 1</div>
<div role="tabpanel" id="panel2" hidden>Content 2</div>
```

### Modal Dialog
```html
<div role="dialog" aria-modal="true" aria-labelledby="title">
  <h2 id="title">Dialog Title</h2>
  <!-- Focus trap here -->
</div>
```

### Live Region
```html
<div aria-live="polite">Status updates appear here</div>
<div aria-live="assertive">Critical errors appear here</div>
```
