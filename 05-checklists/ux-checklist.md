# UX Checklist

A comprehensive checklist for evaluating the user experience of your product.

## User Research

- [ ] Target audience is defined (personas or user profiles)
- [ ] User research conducted (interviews, surveys, or analytics)
- [ ] User goals and pain points identified
- [ ] Competitive analysis completed
- [ ] User journeys mapped

## Information Architecture

- [ ] Navigation structure is logical and shallow (max 3 levels)
- [ ] Labels use user-friendly language (not internal jargon)
- [ ] Related content is grouped logically
- [ ] Search is available for content-heavy sites
- [ ] Breadcrumbs used for deep hierarchies
- [ ] Card sorting or tree testing conducted (for large sites)

## User Flows

- [ ] Critical user flows are mapped (signup, checkout, core task)
- [ ] Each flow has a clear start and end
- [ ] Happy path and error paths are designed
- [ ] Flows are as short as possible (minimize steps)
- [ ] Users can go back at any step
- [ ] Progress is visible in multi-step flows

## Forms & Input

- [ ] Only essential fields are included
- [ ] Fields are logically grouped
- [ ] Labels are clear and above inputs
- [ ] Inline validation on blur (not just on submit)
- [ ] Error messages are specific and actionable
- [ ] Required fields are marked
- [ ] Smart defaults and autocomplete used
- [ ] Password fields have show/hide toggle
- [ ] Appropriate input types (email, tel, date pickers)

## Feedback & Communication

- [ ] Every action provides feedback (visual, text, or audio)
- [ ] Loading states for all async operations
- [ ] Success confirmations after key actions
- [ ] Error states with recovery paths
- [ ] Empty states with helpful CTAs
- [ ] Toasts auto-dismiss (3-5s) but can be manually closed
- [ ] Destructive actions require confirmation

## Navigation & Wayfinding

- [ ] User always knows where they are (current page indicator)
- [ ] User can always get back (back button, breadcrumbs, logo → home)
- [ ] Primary navigation is visible (not hidden behind hamburger on desktop)
- [ ] Navigation items are limited (7 max for top nav, 5 for bottom tabs)
- [ ] Search is easily accessible
- [ ] Recently viewed or quick access available (if applicable)

## Error Handling

- [ ] Errors are prevented (validation, disabled states, confirmations)
- [ ] Error messages are: specific, human, actionable
- [ ] Errors don't blame the user
- [ ] Users can recover from errors (undo, retry, alternative path)
- [ ] 404 pages are helpful (search, popular links, home link)
- [ ] Form errors are shown inline (not just at top)
- [ ] Failed actions don't lose user input

## Performance & Perception

- [ ] Interactions respond in <100ms
- [ ] Skeleton screens for content loading
- [ ] Optimistic UI updates where appropriate
- [ ] Images are lazy loaded
- [ ] Large lists are virtualized or paginated
- [ ] Perceived performance is optimized (transitions, progress)

## Onboarding

- [ ] First-time user experience is designed
- [ ] Value proposition is clear within 30 seconds
- [ ] Progressive onboarding (don't teach everything at once)
- [ ] Empty states guide first actions
- [ ] Tooltips or coach marks for key features
- [ ] Skip option for onboarding

## Trust & Transparency

- [ ] Privacy policy and terms are accessible
- [ ] Data collection is transparent (what and why)
- [ ] Security indicators where needed (HTTPS, badges)
- [ ] Pricing is clear (no hidden fees)
- [ ] No dark patterns (forced continuity, confirmshaming, trick questions)
- [ ] Easy to delete account or unsubscribe

## Mobile Experience

- [ ] Thumb-friendly design (primary actions in bottom 1/3)
- [ ] No hover-dependent functionality (touch alternative exists)
- [ ] Appropriate keyboards triggered (email, tel, numeric)
- [ ] No zoom required to read text
- [ ] Forms are minimal on mobile
- [ ] Gestures are intuitive (swipe back, pull to refresh)
- [ ] Respects safe areas (notch, home indicator)

## Content & Readability

- [ ] Content is scannable (headings, bullets, short paragraphs)
- [ ] Reading level is appropriate for the audience
- [ ] No walls of text (break up with headings, images, whitespace)
- [ ] Important information is above the fold
- [ ] Instructions are clear and concise
- [ ] Tone is consistent and appropriate

## Accessibility (Quick Check)

- [ ] Keyboard navigation works for all interactions
- [ ] Visible focus indicators on all focusable elements
- [ ] Color contrast meets WCAG AA (4.5:1 for text)
- [ ] Images have alt text
- [ ] Forms have proper labels
- [ ] Semantic HTML used
- [ ] Page works at 200% zoom
- [ ] Respects `prefers-reduced-motion`

## Analytics & Iteration

- [ ] Analytics tracking is set up
- [ ] Key funnels are defined and tracked
- [ ] Conversion goals are measurable
- [ ] Feedback mechanism available (contact, rating, survey)
- [ ] Usability testing planned post-launch
- [ ] A/B testing framework available
