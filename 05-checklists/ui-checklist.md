# UI Design Checklist

A comprehensive checklist for reviewing UI designs before handoff or launch.

## Layout & Structure

- [ ] Content is organized in a clear visual hierarchy
- [ ] One primary action is visible per screen/section
- [ ] Whitespace is used to separate and group related content
- [ ] Content width is constrained for readability (max 65-75 chars for text)
- [ ] Layout follows a consistent grid system (8px base)
- [ ] Alignment is consistent (left, center, or right — not mixed)
- [ ] No horizontal scroll on any breakpoint

## Typography

- [ ] Font sizes follow a consistent type scale
- [ ] Body text is minimum 16px
- [ ] Line height is 1.5-1.6 for body text
- [ ] No more than 3 font weights used
- [ ] No more than 2 font families (sans + mono, or serif + sans)
- [ ] Headings have clear visual distinction from body text
- [ ] Text contrast meets WCAG AA (4.5:1 minimum)
- [ ] No all-caps for body text
- [ ] Text is not justified (left-aligned in LTR languages)

## Color

- [ ] Color palette is limited (1 primary + semantic + neutrals)
- [ ] 60-30-10 rule applied (dominant, secondary, accent)
- [ ] Color is not the sole indicator of meaning (paired with icon/text)
- [ ] Semantic colors used correctly (success=green, error=red, warning=amber, info=blue)
- [ ] Dark mode palette is defined (not just inverted)
- [ ] All colors use design tokens, not hardcoded values

## Components

- [ ] Buttons have clear hierarchy (primary, secondary, tertiary)
- [ ] All button states designed (default, hover, focus, active, disabled, loading)
- [ ] Form inputs have labels (not just placeholders)
- [ ] Error states designed for all forms
- [ ] Empty states designed (no data, no results, error)
- [ ] Loading states designed (skeletons or spinners)
- [ ] Modals have close button, overlay click, and Esc to close
- [ ] Navigation shows current page/section
- [ ] All interactive elements have hover and focus states
- [ ] Touch targets are minimum 44×44px

## Icons & Images

- [ ] Icons are from a consistent library (same style, stroke width)
- [ ] Icons are paired with text labels for critical actions
- [ ] Images use consistent aspect ratios
- [ ] Image placeholders designed for loading state
- [ ] Fallback images for missing/failed images
- [ ] Icons use `currentColor` for easy theming

## Spacing

- [ ] Spacing follows the 8px grid (4px for fine adjustments)
- [ ] Consistent padding within similar components
- [ ] Section spacing is 32-64px
- [ ] Component padding is 16-24px
- [ ] Inline spacing (icon to text) is 8px
- [ ] No random or inconsistent spacing values

## Responsive

- [ ] Mobile layout designed (375px)
- [ ] Tablet layout designed (768px)
- [ ] Desktop layout designed (1024px+)
- [ ] Wide screen layout designed (1440px+)
- [ ] Navigation adapts (hamburger on mobile, full on desktop)
- [ ] Grid columns adjust per breakpoint
- [ ] Font sizes scale appropriately
- [ ] Touch targets are large enough on mobile

## Visual Polish

- [ ] Shadows are consistent (same elevation = same shadow)
- [ ] Border radius is consistent across components
- [ ] No mismatched border colors or thicknesses
- [ ] Images are not stretched or distorted
- [ ] No z-index issues (overlapping elements)
- [ ] Scrollbars styled if visible
- [ ] Favicon designed
- [ ] 404 and error pages designed

## Consistency

- [ ] Same component looks the same everywhere
- [ ] Same spacing patterns used across pages
- [ ] Same color usage for same purposes
- [ ] Same icon style throughout
- [ ] Same button styles for same action types
- [ ] Design system components used (no one-off styles)

## Content

- [ ] Real or realistic content used (not lorem ipsum)
- [ ] Button labels are action-oriented ("Save" not "Saved")
- [ ] Error messages are specific, human, and actionable
- [ ] Empty state messages are helpful and encouraging
- [ ] Microcopy is clear and concise
- [ ] Character limits considered for dynamic content
- [ ] Long text handling designed (truncation, wrapping)

## Handoff Readiness

- [ ] All screens are in the design file
- [ ] Layers are named clearly
- [ ] Components are properly created (not flattened)
- [ ] Auto layout used where applicable
- [ ] Prototype flows are set up
- [ ] Assets are exported (SVG icons, optimized images)
- [ ] Design tokens are defined
- [ ] Annotations added for complex interactions
