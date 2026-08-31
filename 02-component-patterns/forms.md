# Forms

## Form Design Principles

1. **Minimize fields** — every field is friction. Remove what's not essential.
2. **One column** — multi-column forms have lower completion rates.
3. **Clear labels** — users should never guess what to enter.
4. **Inline validation** — validate as the user types or on blur, not just on submit.
5. **Forgiving inputs** — accept varied formats (phone, date) when possible.

## Form Layout

### Single Column (Recommended)
```
┌─────────────────────────┐
│  Create Account          │
│                          │
│  Full name               │
│  [____________________]  │
│                          │
│  Email                   │
│  [____________________]  │
│                          │
│  Password                │
│  [____________________]  │
│                          │
│  [   Create Account  ]  │
│                          │
│  Already have an account?│
│  Sign in                 │
└─────────────────────────┘
```

### Multi-Column (Use Sparingly)
- Only for related fields on the same row (e.g., First Name + Last Name)
- Only for short forms (checkout: city + state + zip)
- Never for long forms

### Grouping
- Use `<fieldset>` + `<legend>` for logical groups
- Break long forms into steps (wizard/multi-step)

## Input Types

### Text Input
```
  Label
┌───────────────────────┐
│ Placeholder text...    │
└───────────────────────┘
  Helper text (optional)
```

### Variants
| Type | HTML | Use For |
|---|---|---|
| Text | `type="text"` | Names, titles, free text |
| Email | `type="email"` | Email addresses (validates format) |
| Password | `type="password"` | Passwords (show/hide toggle) |
| Number | `type="number"` | Quantities (use steppers for small ranges) |
| Tel | `type="tel"` | Phone numbers |
| URL | `type="url"` | Web addresses |
| Search | `type="search"` | Search fields (shows clear button) |
| Date | `type="date"` | Dates (use native picker) |
| Time | `type="time"` | Times |
| Color | `type="color"` | Color selection |

### Textarea
- Auto-resize as user types
- Show character count if there's a limit
- Minimum 3 rows visible

### Select / Dropdown
```
┌───────────────────────┐
│  Selected option    ▼ │
└───────────────────────┘
```
- Use for 4+ options (fewer = use radio buttons)
- Searchable for long lists (10+ items)
- Show selected state clearly
- Allow keyboard navigation (arrow keys)

### Radio Buttons
```
  ( ) Option A
  (•) Option B  ← selected
  ( ) Option C
```
- Use for 2-5 mutually exclusive options
- All options visible at once
- Always show selected state

### Checkboxes
```
  [✓] I agree to the terms
  [ ] Subscribe to newsletter
```
- Use for independent yes/no choices
- Group with fieldset when multiple related options
- Indeterminate state for "some selected" in parent

### Toggle / Switch
```
  Notifications  [ON ●━━]
```
- Use for instant-effect settings (no save needed)
- Not for forms that require submission
- Clearly show on/off state

### Slider
```
  Volume: ━━━●━━━━━ 60%
```
- Use for approximate ranges
- Show current value
- Add tick marks for discrete values

### File Upload
- Drag-and-drop zone with clear border
- Show accepted file types and max size
- Preview uploaded files (images, documents)
- Show upload progress
- Allow removal before submission

## Labels

### Best Practices
- **Always visible** — don't use placeholder as label
- **Top-aligned** (recommended) — fastest completion
- **Left-aligned** — good for scanning, but needs more horizontal space
- **Right-aligned** — compact but harder to scan
- **Short and clear** — "Email" not "Please enter your email address"
- **Sentence case** — "First name" not "First Name"

### Placeholder vs. Label
```
  Bad:
  ┌───────────────────────┐
  │ Enter your email...    │  ← disappears on focus, context lost
  └───────────────────────┘

  Good:
  Email
  ┌───────────────────────┐
  │ name@example.com       │  ← label stays, placeholder shows format
  └───────────────────────┘
```

## Validation

### When to Validate
| Timing | When | Example |
|---|---|---|
| **On blur** | After leaving field | Email format, username availability |
| **On change** | As user types | Password strength meter |
| **On submit** | When form submitted | Cross-field validation, server-side |

### Error Display
```
  Email
  ┌───────────────────────┐
  │ john@                 │  ← red border
  └───────────────────────┘
  ⚠ Please enter a valid email address
```

### Error Message Rules
- **Specific:** "Password must be at least 8 characters" not "Invalid password"
- **Human:** "This email is already registered. Would you like to sign in?" not "Error 409"
- **Actionable:** Tell the user how to fix it
- **Inline:** Show error next to the field, not in a summary at top
- **Polite:** Don't blame the user ("Please enter..." not "You entered wrong...")

### Success States
- Green checkmark or border for valid fields
- Don't overdo it — only show for fields that had errors

## Required Fields

- Mark with `*` asterisk
- Explain at form top: "* Required fields"
- Use HTML5 `required` attribute
- Use `aria-required="true"` for screen readers
- Don't mark everything required — only truly required fields

## Helper Text

- Show below the input
- Use for: format hints, constraints, examples
- Keep it short
- Example: "MM/DD/YYYY" or "8+ characters with a number"

## Password Fields

- Always provide show/hide toggle (eye icon)
- Show strength meter for account creation
- List requirements visibly
- Don't over-restrict (max length, special chars) — follow NIST guidelines

## Multi-Step Forms / Wizards

```
  Step 1 ●━━○━━○━━○ Step 5
  Account → Profile → Preferences → Payment → Review
```

### Guidelines
- Show progress indicator
- Allow back navigation
- Save state between steps
- Show step title and number
- Don't make steps too granular (3-5 steps max)
- Allow review before final submission

## Smart Defaults & Autocomplete

- Pre-fill fields when data is known (country, currency, timezone)
- Use `autocomplete` attributes for common fields
- Use browser autofill-compatible field names
- Remember user preferences between sessions

```html
<input type="email" name="email" autocomplete="email" />
<input type="tel" name="phone" autocomplete="tel" />
<input type="text" name="address" autocomplete="street-address" />
```

## Form Actions

### Primary vs. Secondary
- **Submit** — primary button (filled, brand color)
- **Cancel** — secondary button (outlined or text)
- Submit on the right, cancel on the left (web convention)

### Submit Behavior
- Disable submit while processing
- Show loading state on button
- Don't disable submit until all valid — let users attempt submit to see errors
- On success: redirect or show success message
- On error: scroll to first error, focus the field

## Mobile Forms

- Use appropriate input types (triggers correct keyboard)
- `inputmode` for fine-grained keyboard control
- Minimize typing — use selects, toggles, pickers
- Large touch targets (48px min height)
- Test with one-handed use in mind
- Consider sticky submit button for long forms

## Do's and Don'ts

### Do
- Minimize the number of fields
- Use inline validation
- Provide clear error messages
- Group related fields
- Use appropriate input types
- Show required field indicators
- Allow autofill/autocomplete

### Don't
- Use placeholder text as a label
- Clear fields on validation error
- Use only color to indicate errors
- Force a specific format without telling the user
- Put all errors at the top of the form
- Use dropdowns for 2-3 options (use radio buttons)
- Auto-advance to the next field (frustrating and error-prone)
