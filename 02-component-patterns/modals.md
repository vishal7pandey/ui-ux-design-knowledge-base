# Modals & Overlays

## What Is a Modal?

A modal is an overlay that sits on top of the page content, requiring user interaction before returning to the main interface. It focuses attention on a single task or piece of information.

## When to Use Modals

### Use a Modal When:
- **Focused task:** Login, quick edit, confirmation
- **Critical decision:** Delete confirmation, irreversible action
- **Quick form:** Subscribe, feedback, short input
- **Media viewing:** Image lightbox, video player
- **Details without navigation:** Preview a record without leaving the list

### Don't Use a Modal When:
- **Multi-step workflows** — use a page or wizard instead
- **Complex forms** — use a dedicated page
- **Non-blocking information** — use a toast, banner, or side panel
- **Settings** — use a page or side panel
- **Content that needs scrolling** — if it doesn't fit, use a page

## Modal Types

### Dialog (Standard)
```
  ┌───────────────────────────────┐
  │  Title                    [×] │
  ├───────────────────────────────┤
  │                               │
  │  Content goes here...         │
  │                               │
  │         [Cancel]  [Confirm]   │
  └───────────────────────────────┘
```

### Confirmation Dialog
```
  ┌───────────────────────────────┐
  │  Delete project?          [×] │
  │                               │
  │  This action cannot be undone.│
  │  Type "My Project" to confirm.│
  │                               │
  │  [________________________]   │
  │                               │
  │       [Cancel]  [Delete]      │
  └───────────────────────────────┘
```

### Form Modal
- Contains a short form (3-5 fields max)
- Submit and Cancel buttons at the bottom
- Validate inline

### Media Modal (Lightbox)
- Full-screen or near-full-screen
- Image or video centered
- Close on click outside, Esc, or X button
- Optional: prev/next navigation for galleries

### Side Panel / Drawer
```
  ┌───────────────────────────────────────┐
  │                          ┌──────────┐ │
  │  Main content            │  Panel   │ │
  │  (dimmed)                │          │ │
  │                          │  Content │ │
  │                          │          │ │
  │                          └──────────┘ │
  └───────────────────────────────────────┘
```
- Slides in from the right (or left)
- Less disruptive than a centered modal
- Good for details, settings, filters
- Can be dismissible or persistent

### Bottom Sheet (Mobile)
```
  ┌───────────────────────────────┐
  │  Main content (dimmed)         │
  ├───────────────────────────────┤
  │  ─── (drag handle)            │
  │                               │
  │  Sheet content                │
  │                               │
  │  [Action]                     │
  └───────────────────────────────┘
```
- Slides up from the bottom
- Common on mobile (iOS/Android)
- Can be dismissible by swipe down
- Good for actions and short forms on mobile

## Modal Design Guidelines

### Sizing
| Type | Width | Max Height |
|---|---|---|
| Alert/Confirm | 320–400px | Auto (content-based) |
| Standard dialog | 480–640px | 80vh |
| Form modal | 480–600px | 80vh |
| Side panel | 400–500px | 100vh |
| Full-screen modal (mobile) | 100vw | 100vh |

### Structure
1. **Header:** Title + close button (optional)
2. **Body:** Content (text, form, media)
3. **Footer:** Actions (buttons), right-aligned

### Overlay / Scrim
- Semi-transparent background: `rgba(0, 0, 0, 0.5)` to `rgba(0, 0, 0, 0.7)`
- Click on scrim to dismiss (unless dialog is non-dismissible)
- Blur background for premium feel: `backdrop-filter: blur(4px)`

### Close Methods
- X button in header
- Click on overlay/scrim
- Esc key
- Submit/confirm action (auto-close on success)
- Swipe down (bottom sheets on mobile)

### Non-Dismissible Modals
- Use sparingly — only when the user MUST interact
- Remove X button
- Don't close on overlay click or Esc
- Example: Required terms acceptance, critical error

## Modal Accessibility

### Focus Management
- **On open:** Move focus to the modal (first focusable element or the modal container)
- **On close:** Return focus to the element that triggered the modal
- **Focus trap:** Tab should cycle within the modal, not escape to the background
- **Screen reader:** Use `role="dialog"` and `aria-modal="true"`

```html
<div role="dialog" aria-modal="true" aria-labelledby="modal-title">
  <h2 id="modal-title">Delete project?</h2>
  ...
</div>
```

### Keyboard
- `Esc` closes the modal
- `Tab` cycles through focusable elements within the modal
- `Shift + Tab` cycles backward
- Don't allow focus to leave the modal while open

### Body Scroll Lock
Prevent background scrolling when modal is open:
```css
body.modal-open {
  overflow: hidden;
}
```

## Modal Animation

### Open
- Fade in overlay (200ms)
- Scale up modal from 0.95 to 1.0 + fade in (200-300ms)
- Or slide up from bottom (mobile bottom sheet)

### Close
- Fade out overlay (150ms)
- Scale down modal to 0.95 + fade out (150-200ms)
- Or slide down (bottom sheet)

### Timing
- Open: 200–300ms (slightly slower, user initiated)
- Close: 150–200ms (slightly faster, user wants it gone)

## Stacked Modals

- Avoid stacking modals on top of modals
- If necessary, dim the lower modal further
- Close top modal first, then lower ones
- Better alternative: use a wizard/stepper within a single modal

## Do's and Don'ts

### Do
- Keep modal content concise
- Provide clear title and close button
- Use for focused, single-purpose interactions
- Manage focus properly for accessibility
- Lock body scroll
- Animate open/close smoothly

### Don't
- Use modals for complex, multi-step tasks
- Stack multiple modals
- Make modals taller than the viewport (use a page instead)
- Hide the close button
- Use modals for non-essential information
- Forget to return focus to the trigger element on close
