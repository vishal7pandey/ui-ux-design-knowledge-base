# Buttons

## Button Hierarchy

Every screen should have a clear button hierarchy. Limit to 3 levels:

| Level | Style | Purpose | Example |
|---|---|---|---|
| **Primary** | Filled, brand color | Main action on the screen | "Save", "Submit", "Checkout" |
| **Secondary** | Outlined or subtle fill | Alternative / supporting action | "Cancel", "Back", "Filter" |
| **Tertiary** | Text only / ghost | Low-priority actions | "Learn more", "Skip" |

## Button Types

### Standard Button
```
┌──────────────────┐
│   Save Changes   │
└──────────────────┘
```
- Filled background, white or contrasting text
- Used for primary actions

### Outlined Button
```
┌──────────────────┐
│   Cancel         │  ← border only, transparent bg
└──────────────────┘
```
- Border in brand or neutral color
- Used for secondary actions

### Text / Ghost Button
```
   Learn more →
```
- No background or border
- Used for tertiary actions, inline links

### Icon Button
```
   ⚙️   ← icon only
```
- Must have `aria-label` for accessibility
- Minimum 44×44px touch target
- Use for toolbar actions, settings, close

### FAB (Floating Action Button)
- Circular, elevated, primary brand color
- Used for the most common action on mobile
- Position: bottom-right, above content
- Max 1 per screen

### Toggle Button
- Changes state on click (active/inactive)
- Show active state clearly (filled vs. outlined)

### Split Button
```
┌──────────────┬───┐
│  Save        │ ▼ │
└──────────────┴───┘
```
- Primary action + dropdown for related options
- Use when an action has variations

## Button States

Every button must have these states:

| State | Visual Treatment | Trigger |
|---|---|---|
| **Default** | Normal styling | Resting state |
| **Hover** | Slight darkening / elevation | Mouse over |
| **Focus** | Focus ring (2px outline, offset) | Keyboard navigation |
| **Active/Pressed** | Darker / inset | Mouse down / touch |
| **Disabled** | 50% opacity, no pointer | `disabled` attribute |
| **Loading** | Spinner + disabled | Async action in progress |

### CSS State Implementation
```css
.btn { /* default */ }
.btn:hover { /* hover */ }
.btn:focus-visible { outline: 2px solid var(--color-focus); outline-offset: 2px; }
.btn:active { /* pressed */ }
.btn:disabled { opacity: 0.5; cursor: not-allowed; }
```

## Button Sizing

| Size | Padding (V/H) | Font Size | Min Height | Use Case |
|---|---|---|---|---|
| Small | 6px / 12px | 13px | 32px | Compact UI, table rows |
| Medium | 10px / 20px | 14px | 40px | Default, most UIs |
| Large | 14px / 28px | 16px | 48px | Hero CTAs, mobile |

> **Mobile:** Use large (48px min height) for all primary actions to meet touch target requirements.

## Button Content

### Labels
- **Action-oriented:** "Save" not "Saved", "Delete" not "Deletion"
- **Short:** 1–3 words max
- **Sentence case:** "Save changes" not "Save Changes"
- **Verbs preferred:** "Download report" not "Report"

### Icons
- Icon + text: Icon on the left, text on the right
- Icon only: Must have `aria-label`
- Don't use icons that contradict the label

### Loading State
- Replace button content with spinner + keep label visible
- Disable the button to prevent double-clicks
- Keep button width stable (don't let it shrink)

## Button Placement

### Forms
- **Primary action:** Left or right? Follow platform convention:
  - Web: Primary on the right, secondary on the left
  - iOS: Primary on the right
  - Android: Primary on the right
- **Single button:** Align to the direction of reading (left in LTR)

### Dialogs / Modals
- **Primary action:** Right
- **Secondary/dismiss:** Left
- **Destructive primary:** Use red/warning color + confirmation

### Cards
- Place at bottom of card
- Full-width on mobile
- Auto-width on desktop

### Toolbars
- Group related actions
- Primary action at the start or end
- Overflow menu for less common actions

## Destructive Actions

### Guidelines
1. **Use warning color** (red) for destructive buttons.
2. **Require confirmation** for irreversible actions.
3. **Label clearly:** "Delete project" not just "Delete".
4. **Provide undo** when possible instead of confirmation.
5. **Never make destructive action the default.**

### Confirmation Pattern
```
┌──────────────────────────────────┐
│  Delete project?                  │
│                                   │
│  This will permanently delete     │
│  "My Project" and all its data.   │
│  This action cannot be undone.    │
│                                   │
│       [Cancel]    [Delete]        │
└──────────────────────────────────┘
```

## Button Group

When multiple buttons are related:

```
┌────────┬────────┬────────┐
│  Left  │ Center │  Right │   ← connected, segmented
└────────┴────────┴────────┘
```

- Use for toggling between views (list/grid/table)
- Equal width buttons
- Active state clearly indicated

## Do's and Don'ts

### Do
- One primary button per section
- Consistent sizing within a group
- Clear, action-oriented labels
- Visible focus state
- Loading state for async actions

### Don't
- Multiple primary buttons competing for attention
- Buttons that are too small to tap (< 40px height)
- Using "Submit" as a label (be specific: "Create account")
- Disabling buttons without explanation
- Using icons without labels for critical actions
