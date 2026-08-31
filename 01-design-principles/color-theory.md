# Color Theory for UI/UX

## The 60-30-10 Rule

A classic interior design principle that works perfectly for UI:

- **60%** — Dominant color (usually your background / neutral)
- **30%** — Secondary color (cards, sidebars, secondary surfaces)
- **10%** — Accent color (CTAs, highlights, important elements)

## Color Schemes

### Monochromatic
One hue, varying lightness/saturation. **Safe, clean, elegant.** Great for minimal designs.

### Analogous
Colors adjacent on the color wheel. **Harmonious, calming.** Good for dashboards and data-heavy interfaces.

### Complementary
Opposite colors on the wheel. **High contrast, energetic.** Use sparingly — one as dominant, the other as accent.

### Triadic
Three evenly spaced colors. **Vibrant, balanced.** Works well for playful brands but needs careful balance.

## Color Roles in UI

| Role | Purpose | Example |
|---|---|---|
| **Primary** | Brand color, main CTAs | Blue button |
| **Secondary** | Supporting actions | Outlined button |
| **Surface** | Backgrounds, cards | White, light gray |
| **Text** | Content and labels | Near-black, dark gray |
| **Success** | Positive feedback | Green |
| **Warning** | Caution | Amber/Orange |
| **Error** | Errors, destructive | Red |
| **Info** | Neutral information | Blue (lighter than primary) |

## Contrast & Accessibility

### WCAG Contrast Ratios

| Level | Normal Text | Large Text (18pt+) | UI Components |
|---|---|---|---|
| **AA** (minimum) | 4.5:1 | 3.0:1 | 3.0:1 |
| **AAA** (enhanced) | 7.0:1 | 4.5:1 | — |

### Tips
- Never use pure black (#000) on pure white (#FFF) — it's harsh. Use near-black (#1a1a1a) instead.
- Test contrast with [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/).
- Don't rely on color alone — pair with icons, text, or patterns.

## Dark Mode

### Guidelines
- Don't just invert colors. Dark mode needs its own palette.
- Use desaturated colors — saturated colors vibrate on dark backgrounds.
- Elevate surfaces with lighter shades, not borders.
- Reduce contrast slightly for body text to reduce eye strain (but stay above AA).
- Shadows are less visible — use elevation/lighter surfaces instead.

### Dark Mode Palette Structure
```
Background:      #121212  (or very dark gray)
Surface 1:       #1E1E1E  (cards)
Surface 2:       #242424  (elevated cards)
Surface 3:       #2C2C2C  (modals, popovers)
Primary text:    #E0E0E0
Secondary text:  #A0A0A0
Disabled text:   #5A5A5A
```

## Color Psychology

| Color | Emotion | Common Uses |
|---|---|---|
| **Blue** | Trust, calm, professional | Finance, tech, healthcare |
| **Green** | Growth, success, nature | Sustainability, success states |
| **Red** | Urgency, error, passion | Errors, sales, food |
| **Yellow** | Energy, caution, optimism | Warnings, creative brands |
| **Orange** | Friendly, enthusiastic | Call-to-action, food, sports |
| **Purple** | Luxury, creativity, mystery | Beauty, education, luxury |
| **Pink** | Playful, romantic | Fashion, beauty, youth brands |
| **Black** | Premium, bold, elegant | Luxury, fashion, photography |
| **White** | Clean, minimal, pure | Healthcare, minimalism, tech |

## Practical Tips

1. **Start with grayscale.** Design the layout and hierarchy first, then add color.
2. **Limit your palette.** 1 primary + 1 secondary + neutrals + semantic colors. That's it.
3. **Use opacity for variations.** Instead of 10 shades of blue, use one blue at different opacities.
4. **Test in context.** Colors look different on different screens and next to other colors.
5. **Consider culture.** Red means "stop" in the West but "luck" in China. Know your audience.

## Color Token Naming

Use semantic names, not visual descriptions:

```css
/* Bad */
.blue-button { background: #2563EB; }
.dark-gray-text { color: #1F2937; }

/* Good */
.btn-primary { background: var(--color-primary); }
.text-primary { color: var(--color-text-primary); }
```

### Recommended Token Scale
```
--color-primary-50   /* lightest */
--color-primary-100
--color-primary-200
--color-primary-300
--color-primary-400
--color-primary-500  /* base */
--color-primary-600
--color-primary-700
--color-primary-800
--color-primary-900  /* darkest */
```

---

## Advanced Color Theory: Balance, Relate, Complete

A more intentional, feeling-first approach to composing palettes (adapted from color theorist Ruxandra Duru's method). Instead of picking colors individually, always evaluate colors **in combination** — color is relative, and our visual system pushes neighboring hues, lightness, and intensity apart. There is no such thing as a "neutral" backdrop; everything affects everything else.

### Basic Properties (Refresher)
| Property | Definition |
|---|---|
| **Hue** | The color itself (red, blue, yellow) — organized on a wheel, warm vs. cool |
| **Intensity (Chroma)** | How close a color is to its most vibrant, pure state |
| **Saturation** | How much gray a color contains (distinct from intensity — a fully saturated color can have low intensity) |
| **Lightness (Value/Tone)** | How light or dark a color is — yellow reads lighter than purple even at "pure" state |

### Step 1: Balance the Stimulation
Think of intensity, hue distance, and light-dark contrast as sliders. Push them up to increase stimulation, down to reduce it — and balance them against each other.

| Slider | Low | High |
|---|---|---|
| **Intensity (via desaturation)** | Sober, nostalgic, melancholic | Joyful (pale saturated) or hard/strong (dark saturated) |
| **Hue distance** | Gentle, harmonious | Activating, satisfying (complementary/distant hues) |
| **Light-dark contrast** | Atmospheric, soothing, stillness | Crisp, energizing, legible |

- Avoid the extremes (understimulation → apathy; overstimulation → irritation).
- **Exception:** vibrant, high-contrast hues of the *same lightness* placed side by side cause visual "vibration" — unpleasant even though each slider looks "balanced" on paper.
- **Atmosphere** = soft light-dark contrast + gradients + fuzzy boundaries. Even vivid colors feel gentler with a blurred edge.
- Scale matters: a tiny surface of vibrant color feels different than a wall of the same color. Micro-shifts (like on natural textures) add subtle stimulation flat colors lack.

### Step 2: Relate the Colors
Colors need a common thread — "glue" — or the palette reads as disjointed. Ways to create relatedness (restrict one property at a time):
- **Shared hue family** — colors from the same region of the wheel
- **Shared lightness** — all colors sit at a similar tone
- **Shared intensity/saturation** — all muted, or all vibrant
- **Bathe in an imaginary light** — under warm light, warm colors stay bright and cool colors desaturate (and vice versa)
- **Bridge colors** — insert a color that reads as a mixture of two parent colors to tie them together (usually muted, sitting between the parent hues)

> The more ways colors relate, the more harmonious — but also more expected. A dose of variation/dissonance adds surprise and stimulation.

### Step 3: Complete the Palette
Complementary and near-complementary pairs feel deeply satisfying because they **complete** each other (blue balances orange; dark emphasizes light).
- Colors need not be maximally intense to generate satisfaction — respect all three properties (hue, lightness, intensity) when applying this.
- **Dramatically different proportions amplify satisfaction.** A palette dominated by warm yellow is balanced by just a *pinch* of cool color — like the first sip of water on a hot day.
- With 3+ hues, pick them so they roughly balance around the color wheel (colorist Donald Kaufman calls this "re-creating light").

### Practical Workflow
1. Do a gut check first: joy, warmth, calm = good sign. Irritation, indifference = keep adjusting.
2. Decide the desired stimulation level for the context (calm dashboard vs. energetic marketing page).
3. Pick a relating strategy so the palette reads as one family.
4. Add one completing/contrasting touch in a small proportion for satisfaction.
5. Let it sit — reassess with fresh eyes before finalizing (a technique borrowed from painters: leave the work up and revisit it the next day).

### Additional Resources
- *Interaction of Color* — Josef Albers
- *The Elements of Color* — Johannes Itten
- *Joyful* — Ingrid Fetell Lee (stimulation and pops of color)
