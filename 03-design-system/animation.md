# Animation & Motion

## Why Motion Matters

- **Guides attention** — directs the user's eye to what matters
- **Provides feedback** — confirms an action occurred
- **Shows relationships** — how elements connect and transition
- **Reduces perceived latency** — makes waiting feel shorter
- **Adds personality** — makes the product feel alive and polished

## Motion Principles

### 1. Purposeful
Every animation should serve a function. If it doesn't help the user understand something, remove it.

### 2. Quick
UI animations should be fast. Users shouldn't wait for animations to complete.

| Type | Duration |
|---|---|
| Micro-interactions | 100–200ms |
| State transitions | 200–300ms |
| Enter/exit animations | 250–400ms |
| Page transitions | 300–500ms |
| Onboarding/educational | 500–1000ms |

### 3. Natural
Use easing curves that mimic real-world physics. Linear motion feels robotic.

### 4. Respectful
Honor `prefers-reduced-motion`. Some users find motion distracting or nauseating.

## Easing Curves

### Standard Easings
```css
/* Ease-out: fast start, slow end (most common for enter animations) */
--ease-out: cubic-bezier(0.0, 0.0, 0.2, 1);

/* Ease-in: slow start, fast end (for exit animations) */
--ease-in: cubic-bezier(0.4, 0.0, 1, 1);

/* Ease-in-out: slow start and end (for state transitions) */
--ease-in-out: cubic-bezier(0.4, 0.0, 0.2, 1);

/* Spring/Bounce: overshoot and settle (for playful interactions) */
--ease-spring: cubic-bezier(0.34, 1.56, 0.64, 1);

/* Linear: constant speed (rarely use in UI) */
--ease-linear: linear;
```

### When to Use Each
| Easing | Use For |
|---|---|
| Ease-out | Elements entering the screen |
| Ease-in | Elements leaving the screen |
| Ease-in-out | Elements moving between positions |
| Spring | Playful, attention-grabbing interactions |
| Linear | Progress bars, loading indicators |

## Animation Types

### 1. Micro-interactions
Small animations on individual elements.

| Trigger | Animation |
|---|---|
| Button hover | Background color change (150ms) |
| Button press | Scale down to 0.97 (100ms) |
| Checkbox toggle | Checkmark draws in (200ms) |
| Toggle switch | Knob slides (200ms) |
| Icon hover | Subtle scale or color shift (150ms) |

### 2. State Transitions
When an element changes its visual state.

| Change | Animation |
|---|---|
| Tab switch | Content fade/slide (200ms) |
| Accordion expand | Height + opacity (250ms) |
| Dropdown open | Scale + fade (200ms) |
| Modal open | Scale from 0.95 + fade (250ms) |
| Toast appear | Slide up + fade (300ms) |

### 3. Enter / Exit
Elements appearing or disappearing from the screen.

| Element | Enter | Exit |
|---|---|---|
| Modal | Scale 0.95→1 + fade in | Scale 1→0.95 + fade out |
| Toast | Slide up + fade in | Slide down + fade out |
| Tooltip | Fade in | Fade out |
| Dropdown | Scale Y 0.95→1 + fade | Scale Y 1→0.95 + fade |
| Page | Fade in | Fade out |

### 4. Loading Animations
| Type | Use For |
|---|---|
| Spinner | Short, indeterminate loading |
| Progress bar | Long, determinate loading |
| Skeleton | Content loading (better perceived perf) |
| Pulse | Subtle background loading |
| Shimmer | Skeleton screens |

### 5. Scroll Animations
| Type | Animation |
|---|---|
| Parallax | Background moves slower than foreground |
| Reveal on scroll | Elements fade/slide in as they enter viewport |
| Sticky headers | Header shrinks or changes style on scroll |
| Scroll-to-top | Button appears after scrolling down |

### 6. Drag & Drop
| Stage | Animation |
|---|---|
| Pick up | Element scales up slightly, shadow increases |
| Dragging | Element follows cursor/pointer with slight lag |
| Hover target | Target area highlights |
| Drop | Element settles into place with spring |
| Reorder | Other items shift smoothly to make room |

## Page Transitions

### Fade
```css
.page-enter { opacity: 0; }
.page-enter-active { opacity: 1; transition: opacity 200ms; }
```

### Slide
```css
.page-enter { transform: translateX(100%); }
.page-enter-active { transform: translateX(0); transition: transform 300ms ease-out; }
```

### Shared Element
Elements that appear on both pages animate smoothly between positions:
- Avatar in a list → profile page header
- Card → detail page
- Thumbnail → full-screen image

## CSS Animation vs. JavaScript

### CSS (Preferred for simple animations)
```css
.button {
  transition: background-color 150ms ease, transform 100ms ease;
}
.button:hover { background-color: var(--color-primary-hover); }
.button:active { transform: scale(0.97); }
```

**Use CSS when:**
- Simple state transitions (hover, focus, active)
- Showing/hiding elements
- Color, opacity, transform changes
- No complex sequencing needed

### JavaScript (For complex animations)
```tsx
import { animate } from 'framer-motion';

animate(element, { x: 100, opacity: 1 }, { duration: 0.3, ease: 'easeOut' });
```

**Use JS when:**
- Physics-based animations (spring, momentum)
- Choreographed sequences (multiple elements, staggered)
- Drag interactions
- Layout animations (FLIP technique)
- Animating between unrelated elements

## Performance

### What to Animate
| Property | Performance |
|---|---|
| `transform` (translate, scale, rotate) | ✅ GPU-accelerated, best performance |
| `opacity` | ✅ GPU-accelerated, excellent |
| `color`, `background-color` | ⚠️ CPU, repaint — OK for small areas |
| `width`, `height` | ❌ Causes layout reflow — avoid |
| `top`, `left`, `margin` | ❌ Causes layout reflow — avoid |

### Rules
1. **Animate `transform` and `opacity`** — never animate `width`, `height`, `top`, `left`
2. **Use `will-change`** sparingly — only on elements that will animate
3. **Avoid animating filters** (blur, drop-shadow) — expensive
4. **Limit simultaneous animations** — max 3-4 at a time
5. **Use `transform: translateZ(0)`** to force GPU layer when needed

### `will-change`
```css
.modal {
  will-change: transform, opacity;
}
/* Remove after animation completes to free memory */
```

## Reduced Motion

### Implementation
```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

### Guidelines
- Don't remove all motion — some users still want subtle feedback
- Replace motion with instant state changes
- Keep opacity changes (they don't cause motion sickness)
- Provide a manual toggle in settings if possible

## Animation Libraries

| Library | Type | Best For |
|---|---|---|
| [Framer Motion](https://www.framer.com/motion/) | React | Component animations, gestures, layout animations |
| [React Spring](https://react-spring.dev/) | React | Physics-based animations |
| [GSAP](https://greensock.com/gsap/) | Vanilla JS | Complex timelines, SVG animations |
| [Lottie](https://lottiefiles.com/) | Multi-platform | After Effects animations, illustrations |
| [Anime.js](https://animejs.com/) | Vanilla JS | Lightweight, SVG morphing |
| [Auto-Animate](https://auto-animate.formkit.com/) | Framework-agnostic | Zero-config layout animations |
| [Motion One](https://motion.dev/) | Vanilla JS | Web Animations API, lightweight |

## Do's and Don'ts

### Do
- Keep animations fast (150–300ms for most UI)
- Use easing curves, not linear
- Animate transform and opacity only
- Respect `prefers-reduced-motion`
- Use animations to guide, not decorate
- Test on low-end devices

### Don't
- Animate layout properties (width, height, top, left)
- Make animations longer than 500ms (except onboarding)
- Use bounce/spring for serious interfaces
- Animate everything — be selective
- Block user interaction during animations
- Use autoplaying animations that can't be paused
