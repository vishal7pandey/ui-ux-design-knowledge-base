# Feedback & Notifications

## Feedback Types

| Type | Duration | Purpose | Example |
|---|---|---|---|
| **Toast** | 3-5 seconds | Brief confirmation | "Saved successfully" |
| **Snackbar** | 3-7 seconds | Confirmation + action | "Email sent. Undo" |
| **Banner** | Until dismissed | Important page-level info | "Maintenance scheduled" |
| **Alert / Callout** | Persistent | Critical info in context | "This field is required" |
| **Notification** | Until read | Out-of-context updates | "New comment on your post" |
| **Progress indicator** | During task | Task in progress | Spinner, progress bar |
| **Empty state** | Persistent | No data to show | "No results found" |
| **Error state** | Until resolved | Something went wrong | "Failed to load data" |

## Toasts

```
                    ┌──────────────────────┐
                    │  ✓ Saved successfully │
                    └──────────────────────┘
```

### Guidelines
- **Duration:** 3-5 seconds (longer for longer text)
- **Position:** Top-center or bottom-center (mobile), bottom-right (desktop)
- **Auto-dismiss:** Yes, with a progress bar (optional)
- **Manual dismiss:** Swipe or X button
- **Stacking:** Max 3 visible, queue additional ones
- **Don't use for:** Errors that require action, critical information

### Toast with Action
```
                    ┌──────────────────────────────┐
                    │  Email sent to 3 recipients  │
                    │                       [Undo] │
                    └──────────────────────────────┘
```
- Action button on the right
- Action should be reversible (undo, retry)
- Toast dismisses when action is clicked

### Toast Types
| Type | Color | Icon | Use For |
|---|---|---|---|
| Success | Green | ✓ | Successful operations |
| Error | Red | ✕ | Failed operations |
| Warning | Amber | ⚠ | Cautions, partial success |
| Info | Blue | ℹ | Neutral information |

## Banners

```
┌──────────────────────────────────────────────────────┐
│  ⚠  Scheduled maintenance on Sunday, 2 AM - 4 AM  [×] │
└──────────────────────────────────────────────────────┘
```

### Guidelines
- Full-width, positioned at top of page or section
- Persistent until dismissed or resolved
- Can include an action button or link
- Use for: system announcements, maintenance, policy changes, warnings
- Don't stack multiple banners (combine into one)

### Banner Types
| Type | Color | Use For |
|---|---|---|
| Info | Blue | General announcements |
| Success | Green | Positive news |
| Warning | Amber | Cautions, upcoming changes |
| Error | Red | Critical issues, outages |

## Inline Alerts / Callouts

```
  ┌──────────────────────────────────────┐
  │  ⚠  Please fix the following errors:  │
  │  • Email is required                  │
  │  • Password must be 8+ characters     │
  └──────────────────────────────────────┘
```

### Guidelines
- Positioned in context, near the relevant content
- Persistent (not auto-dismissing)
- Can contain lists, links, or actions
- Use for: form errors, validation messages, contextual warnings

## Progress Indicators

### Spinner
```
        ◌
       (loading)
```
- For indeterminate loading (unknown duration)
- Small: 16-24px (inline), Large: 40-48px (full page)
- Don't use for tasks > 10 seconds (use progress bar instead)

### Progress Bar
```
  ━━━━━━━━━━●━━━━━━━━━━━━  45%
```
- For determinate loading (known progress)
- Show percentage if available
- Smooth animation
- Can show file name, speed, or ETA

### Skeleton Loading
```
  ┌───────────────────────────┐
  │  ░░░░░░░░░░░░░░░░░░░░░░░  │
  │  ░░░░░░░░░░░░░░░░░░       │
  │  ░░░░░░░░░░░░░░░░░░░░░░░  │
  └───────────────────────────┘
```
- Shows the shape of content while it loads
- Better perceived performance than spinners
- Animate with shimmer effect (left-to-right gradient sweep)
- Match the dimensions of the actual content

### Loading Button
```
  ┌──────────────────────┐
  │  ◌  Saving...         │
  └──────────────────────┘
```
- Replace button content with spinner + text
- Disable button to prevent double-submit
- Keep button width stable

## Empty States

### Types
| Type | When | Example |
|---|---|---|
| **No data yet** | New user, nothing created | "No projects yet. Create your first one." |
| **No results** | Search/filter returned nothing | "No results for 'query'. Try different keywords." |
| **Error** | Failed to load data | "Failed to load. Check connection and retry." |
| **No permission** | User lacks access | "You don't have access to this section." |

### Structure
1. **Illustration or icon** — sets the tone
2. **Title** — what happened (short)
3. **Description** — why it happened or what to do
4. **Action** — CTA button to resolve (if applicable)

### Guidelines
- Be helpful, not apologetic (unless it's an error)
- Provide a clear next step
- Use consistent illustrations
- Don't blame the user

## Error States

### Error Display Principles
1. **Be specific** — what exactly went wrong?
2. **Be human** — write in plain language
3. **Be actionable** — what should the user do?
4. **Be visible** — don't hide errors
5. **Be recoverable** — provide a path forward

### Error Types
| Type | Display Method | Example |
|---|---|---|
| Form validation | Inline below field | "Email is required" |
| API error | Toast or inline alert | "Failed to save. Try again." |
| 404 / Not found | Full page error | "Page not found" |
| 500 / Server error | Full page error | "Something went wrong on our end" |
| Network error | Banner or toast | "You're offline. Reconnect to continue." |
| Permission error | Inline or full page | "You don't have permission to view this." |

### Full Page Error
```
    ┌───────────────────────────────┐
    │                               │
    │         🔌                     │
    │     Connection lost            │
    │                               │
    │  Check your internet and      │
    │  try again.                    │
    │                               │
    │       [ Retry ]               │
    │                               │
    └───────────────────────────────┘
```

## Notifications (Push/Badge)

### Badge
```
  ┌──────────┐
  │  Inbox  ③│  ← count badge
  └──────────┘
```
- Small number on an icon or tab
- Shows unread/unprocessed count
- Red for urgent, gray for informational
- Max display "99+" for large numbers

### Notification Panel
- Dropdown panel from a bell icon
- List of recent notifications
- Mark as read / mark all as read
- Group similar notifications
- Show timestamp
- Link to relevant content

### Push Notifications (Mobile)
- Permission-based (ask at the right time)
- Actionable (buttons for quick actions)
- Personalized and relevant
- Don't spam — quality over quantity

## Do's and Don'ts

### Do
- Provide feedback for every user action
- Use toasts for confirmations, not errors
- Show loading states for any async operation
- Make errors actionable and recoverable
- Use skeleton loading for better perceived performance
- Keep notifications relevant and not spammy

### Don't
- Auto-dismiss error toasts before the user can read them
- Use alerts/modals for non-critical information
- Block the UI for non-blocking operations
- Show multiple toasts simultaneously (queue them)
- Use jargon or error codes in user-facing messages
- Forget to handle loading, error, and empty states
