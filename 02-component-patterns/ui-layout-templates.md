# UI Layout Templates

This guide collects established, production-proven page and application templates. These are the patterns that appear in nearly every SaaS, admin, dashboard, and web product; use them as a starting point instead of designing from scratch.

---

## 1. Dashboard Layout

**Use for**: Admin panels, analytics, SaaS home, internal tools.

### Classic sidebar layout

```
┌────────────────────────────────────────────────────────────┐
│  Logo   · Nav ·                   Search  · User menu      │ Top bar
├────────┬───────────────────────────────────────────────────┤
│        │                                                   │
│  Nav   │                 Main content                      │
│  link   │                 (KPIs, charts, tables)            │
│  link   │                                                   │
│  link   │                                                   │
│        │                                                   │
└────────┴───────────────────────────────────────────────────┘
```

### Anatomy

| Region | Purpose | Common components |
|--------|---------|-------------------|
| **Top bar** | Global navigation, user identity, search | Logo, command palette, notifications, profile, theme toggle |
| **Sidebar** | Primary route navigation | Nav links, collapsible groups, active state |
| **Main content** | Screen-specific information | Page header, KPI cards, charts, tables, filters |

### Best practices

- Keep sidebar fixed and scrollable independently.
- Use a clear active state for the current route.
- Provide a mobile drawer or hamburger for narrow screens.
- Sticky top bar keeps global access constant.
- Leave plenty of whitespace; dashboards are dense enough already.

---

## 2. Auth Layout

**Use for**: login, sign-up, forgot password, magic link, MFA, invite flows.

### Centered card layout

```
┌────────────────────────────────────────────────────────────┐
│                                                            │
│                    Logo / product name                     │
│                                                            │
│  ┌────────────────────────────────────────────────────┐   │
│  │                                                    │   │
│  │              Heading (e.g., Sign in)               │   │
│  │                                                    │   │
│  │  [ Social auth buttons ]                           │   │
│  │              ── or continue with ──                │   │
│  │  Email                                             │   │
│  │  [_________________]                               │   │
│  │  Password                                          │   │
│  │  [_________________]                               │   │
│  │  [ Sign in ]                                       │   │
│  │  Forgot password?  ·  Sign up                      │   │
│  └────────────────────────────────────────────────────┘   │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

### Best practices

- Single-column, centered card on desktop; full-bleed form on mobile.
- Keep forms short; split MFA and profile setup into follow-up steps.
- Provide explicit error messages next to the relevant field.
- Show password-strength inline.
- Avoid dark patterns (hiding sign-out, forced email collection).
- Keyboard navigable and screen-reader friendly.

### Common auth routes

- `/login` or `/sign-in`
- `/sign-up`
- `/forgot-password`
- `/reset-password`
- `/verify-email`
- `/onboarding`

---

## 3. Onboarding Wizard

**Use for**: first-run setup, account configuration, guided product activation.

### Stepper layout

```
┌────────────────────────────────────────────────────────────┐
│  Step 1 → Step 2 → Step 3 → Step 4                         │
├────────────────────────────────────────────────────────────┤
│                                                            │
│              Step title and description                    │
│                                                            │
│              [ Form / content for this step ]              │
│                                                            │
│              [ Back ]                [ Next ]              │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

### Best practices

- Show progress (steps completed, current, upcoming).
- Let users skip or exit and resume later.
- Prefill known information; avoid asking the same thing twice.
- Validate each step before allowing forward movement.
- Confirm completion and show the next action.

### Typical 4-step onboarding

1. Profile setup (name, company, role)
2. Team / invite members
3. Import or connect data
4. Preferences and notifications

---

## 4. Settings Layout

**Use for**: account, billing, team, notification, and application preferences.

### Two-column settings shell

```
┌────────────────────────────────────────────────────────────┐
│  Settings                                                  │
├──────────┬─────────────────────────────────────────────────┤
│  Account │                                                 │
│  Billing │              Section title                      │
│  Team    │                                                 │
│  Security│              [ Form fields ]                    │
│  Notif.  │                                                 │
│  Integr. │              [ Save changes ]                   │
│          │                                                 │
└──────────┴─────────────────────────────────────────────────┘
```

### Best practices

- Left navigation for settings categories; URL per tab.
- Group related options visually.
- Use inline editing where possible; avoid full-page reloads.
- Show save / cancel when dirty.
- Separate destructive actions (delete account) into their own section with confirmation.

---

## 5. Detail / Record View

**Use for**: customer profile, lead detail, order detail, document view.

### Split-pane detail layout

```
┌────────────────────────────────────────────────────────────┐
│  ← Back to list          [ Edit ]  [ Actions ▼ ]           │
├────────────────────────────────────────────────────────────┤
│  ┌──────────────┐   ┌─────────────────────────────────┐   │
│  │ Summary      │   │ Tabs: Overview / Activity /     │   │
│  │              │   │       Files / Notes             │   │
│  │ · Status     │   │                                 │   │
│  │ · Owner      │   │  [ Tab content ]                │   │
│  │ · Created    │   │                                 │   │
│  │ · Tags       │   │                                 │   │
│  └──────────────┘   └─────────────────────────────────┘   │
└────────────────────────────────────────────────────────────┘
```

### Best practices

- Persistent "back" link to the list.
- Summary panel for the most important metadata.
- Tabs for related, lower-priority content.
- Prominent actions (edit, delete, share) in the top right.
- Keep the primary record visible while the user switches tabs.

---

## 6. List / Table View

**Use for**: users, orders, customers, products, files.

### Anatomy

```
┌────────────────────────────────────────────────────────────┐
│  Title                              [ New ] [ Filter ]     │
├────────────────────────────────────────────────────────────┤
│  [ Search... ]  [ Filter ▼ ]  [ Sort ▼ ]                   │
├────────────────────────────────────────────────────────────┤
│  □  Name          Status    Created        Actions         │
│  □  Alice Smith   Active    2025-01-12     Edit  Delete    │
│  □  Bob Brown     Pending   2025-02-04     Edit  Delete    │
│  □  Carol White   Active    2024-12-19     Edit  Delete    │
├────────────────────────────────────────────────────────────┤
│  Showing 1–3 of 24         [ < 1 2 3 ... 8 > ]             │
└────────────────────────────────────────────────────────────┘
```

### Best practices

- Keep actions near the row they affect.
- Use bulk selection for mass actions.
- Provide search, filter, and sort controls.
- Pagination for large datasets; virtual scroll for very large ones.
- Empty and loading states are part of the template.
- Keyboard navigation for data tables (arrow keys, enter to open).

---

## 7. Wizard / Multi-Step Form

**Use for**: checkout, application flows, complex configuration, surveys.

### Best practices

- Show step progress and allow backward movement.
- Persist answers across steps.
- Validate on next, not on every keystroke.
- Provide a review step before final submission.
- Allow saving as draft.
- Confirm successful completion and next action.

---

## 8. Marketing / Landing Page Sections

These patterns appear repeatedly in high-converting sites.

| Section | Pattern |
|---------|---------|
| **Hero** | Headline + subheadline + CTA + supporting image/video |
| **Features** | 3–6 feature cards with icon, title, short description |
| **Social proof** | Testimonials, logos, reviews, metrics |
| **Pricing** | 2–4 tiers with feature list and CTA |
| **FAQ** | Accordion of questions |
| **CTA band** | High-contrast banner with single action |
| **Footer** | Links grouped by category, social, newsletter, legal |

---

## 9. Selection Criteria: Which Template?

| Task | Recommended template |
|------|---------------------|
| Monitor data and take action | Dashboard layout |
| Authenticate or register | Auth layout |
| First-time setup | Onboarding wizard |
| Configure preferences | Settings layout |
| View one record | Detail / record view |
| Browse many records | List / table view |
| Complete a multi-step task | Wizard |
| Explain and sell product | Marketing page sections |

---

## 10. Common Anti-Patterns to Avoid

1. **Reinventing the nav** for a pattern that users already know.
2. **Hiding the primary action** in a dropdown instead of the page header.
3. **No empty state** — every list needs one.
4. **Inconsistent form layout** across auth, settings, and wizards.
5. **Mobile as an afterthought** — test drawer, scroll, and touch targets.
6. **Tabs inside tabs** — a sign the template is wrong for the content.
