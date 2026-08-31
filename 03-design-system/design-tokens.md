# Design Tokens

## What Are Design Tokens?

Design tokens are the atomic units of a design system — named values that store visual design attributes (colors, spacing, typography, shadows, etc.) in a platform-agnostic format.

### Why Use Tokens?
- **Consistency:** Same value used everywhere, updated in one place
- **Scalability:** Change a token → updates across the entire product
- **Theming:** Swap token values for dark mode, brands, or white-label
- **Communication:** Shared language between designers and developers
- **Platform-agnostic:** Tokens can be transformed for CSS, iOS, Android, etc.

## Token Architecture

### Three-Tier System

```
Tier 1: Global / Alias Tokens (raw values)
  --color-blue-500: #3B82F6;
  --space-4: 16px;
  --font-size-base: 16px;

Tier 2: Semantic Tokens (purpose-based)
  --color-primary: var(--color-blue-500);
  --color-text-primary: var(--color-gray-900);
  --space-padding-card: var(--space-4);

Tier 3: Component Tokens (component-specific)
  --button-bg-primary: var(--color-primary);
  --button-padding-y: var(--space-3);
  --card-padding: var(--space-padding-card);
```

### Why Three Tiers?
- **Tier 1** defines the raw palette (rarely changes)
- **Tier 2** maps raw values to purposes (changes when rebranding or theming)
- **Tier 3** maps semantic tokens to components (changes when tweaking a specific component)

## Color Tokens

### Raw Color Palette
```css
/* Gray */
--color-gray-50:  #F9FAFB;
--color-gray-100: #F3F4F6;
--color-gray-200: #E5E7EB;
--color-gray-300: #D1D5DB;
--color-gray-400: #9CA3AF;
--color-gray-500: #6B7280;
--color-gray-600: #4B5563;
--color-gray-700: #374151;
--color-gray-800: #1F2937;
--color-gray-900: #111827;

/* Blue (Primary) */
--color-blue-50:  #EFF6FF;
--color-blue-100: #DBEAFE;
--color-blue-200: #BFDBFE;
--color-blue-300: #93C5FD;
--color-blue-400: #60A5FA;
--color-blue-500: #3B82F6;
--color-blue-600: #2563EB;
--color-blue-700: #1D4ED8;
--color-blue-800: #1E40AF;
--color-blue-900: #1E3A8A;

/* Semantic Colors */
--color-success-500: #10B981;
--color-warning-500: #F59E0B;
--color-error-500:   #EF4444;
--color-info-500:    #3B82F6;
```

### Semantic Color Tokens
```css
/* Brand */
--color-primary:     var(--color-blue-500);
--color-primary-hover: var(--color-blue-600);
--color-primary-active: var(--color-blue-700);
--color-primary-light: var(--color-blue-50);

/* Text */
--color-text-primary:   var(--color-gray-900);
--color-text-secondary: var(--color-gray-600);
--color-text-disabled:  var(--color-gray-400);
--color-text-inverse:   #FFFFFF;

/* Backgrounds */
--color-bg-primary:   #FFFFFF;
--color-bg-secondary: var(--color-gray-50);
--color-bg-tertiary:  var(--color-gray-100);
--color-bg-inverse:   var(--color-gray-900);

/* Borders */
--color-border-default: var(--color-gray-200);
--color-border-strong:  var(--color-gray-300);
--color-border-focus:   var(--color-blue-500);

/* Feedback */
--color-success: var(--color-success-500);
--color-warning: var(--color-warning-500);
--color-error:   var(--color-error-500);
--color-info:    var(--color-info-500);
```

## Spacing Tokens

```css
/* Base scale (4px increments) */
--space-0:  0;
--space-1:  4px;
--space-2:  8px;
--space-3:  12px;
--space-4:  16px;
--space-5:  20px;
--space-6:  24px;
--space-8:  32px;
--space-10: 40px;
--space-12: 48px;
--space-16: 64px;
--space-20: 80px;
--space-24: 96px;

/* Semantic spacing */
--space-xs:    var(--space-1);   /* 4px  - tight inline */
--space-sm:    var(--space-2);   /* 8px  - small gaps */
--space-md:    var(--space-4);   /* 16px - default */
--space-lg:    var(--space-6);   /* 24px - section gaps */
--space-xl:    var(--space-8);   /* 32px - large gaps */
--space-2xl:   var(--space-12);  /* 48px - section separation */
--space-3xl:   var(--space-16);  /* 64px - page separation */
```

## Typography Tokens

```css
/* Font families */
--font-family-sans: 'Inter', -apple-system, system-ui, sans-serif;
--font-family-mono: 'JetBrains Mono', 'SF Mono', monospace;
--font-family-serif: 'Georgia', serif;

/* Font sizes */
--font-size-xs:   0.75rem;   /* 12px */
--font-size-sm:   0.875rem;  /* 14px */
--font-size-base: 1rem;      /* 16px */
--font-size-lg:   1.125rem;  /* 18px */
--font-size-xl:   1.25rem;   /* 20px */
--font-size-2xl:  1.5rem;    /* 24px */
--font-size-3xl:  1.875rem;  /* 30px */
--font-size-4xl:  2.25rem;   /* 36px */
--font-size-5xl:  3rem;      /* 48px */

/* Font weights */
--font-weight-regular:  400;
--font-weight-medium:   500;
--font-weight-semibold: 600;
--font-weight-bold:     700;

/* Line heights */
--line-height-none:    1;
--line-height-tight:   1.25;
--line-height-snug:    1.375;
--line-height-normal:  1.5;
--line-height-relaxed: 1.625;
--line-height-loose:   2;

/* Letter spacing */
--letter-spacing-tighter: -0.05em;
--letter-spacing-tight:   -0.025em;
--letter-spacing-normal:  0;
--letter-spacing-wide:    0.025em;
--letter-spacing-wider:   0.05em;
```

## Shadow Tokens

```css
--shadow-none: none;
--shadow-xs: 0 1px 2px rgba(0, 0, 0, 0.05);
--shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.1), 0 1px 2px rgba(0, 0, 0, 0.06);
--shadow-md: 0 4px 6px rgba(0, 0, 0, 0.1), 0 2px 4px rgba(0, 0, 0, 0.06);
--shadow-lg: 0 10px 15px rgba(0, 0, 0, 0.1), 0 4px 6px rgba(0, 0, 0, 0.05);
--shadow-xl: 0 20px 25px rgba(0, 0, 0, 0.1), 0 10px 10px rgba(0, 0, 0, 0.04);
--shadow-2xl: 0 25px 50px rgba(0, 0, 0, 0.25);
```

## Border Radius Tokens

```css
--radius-none:   0;
--radius-sm:     2px;
--radius-md:     4px;
--radius-lg:     8px;
--radius-xl:     12px;
--radius-2xl:    16px;
--radius-full:   9999px;
```

## Z-Index Tokens

```css
--z-base:        0;
--z-dropdown:    100;
--z-sticky:      200;
--z-overlay:     300;
--z-modal:       400;
--z-popover:     500;
--z-toast:       600;
--z-tooltip:     700;
```

## Transition Tokens

```css
--transition-fast:   150ms ease;
--transition-normal: 200ms ease;
--transition-slow:   300ms ease;
--transition-spring: 400ms cubic-bezier(0.34, 1.56, 0.64, 1);

/* Specific transitions */
--transition-colors: 150ms ease;
--transition-opacity: 150ms ease;
--transition-transform: 200ms ease;
--transition-shadow: 200ms ease;
```

## Dark Mode Tokens

```css
/* Light mode (default) */
:root {
  --color-bg-primary:   #FFFFFF;
  --color-bg-secondary: var(--color-gray-50);
  --color-text-primary: var(--color-gray-900);
  --color-text-secondary: var(--color-gray-600);
  --color-border-default: var(--color-gray-200);
}

/* Dark mode */
[data-theme="dark"] {
  --color-bg-primary:   #121212;
  --color-bg-secondary: #1E1E1E;
  --color-bg-tertiary:  #242424;
  --color-text-primary: #E0E0E0;
  --color-text-secondary: #A0A0A0;
  --color-border-default: #333333;
}
```

## Token Tools & Formats

### Style Dictionary
Transform tokens from JSON to CSS, SCSS, iOS, Android, etc.

```json
{
  "color": {
    "primary": {
      "value": "#3B82F6",
      "type": "color"
    }
  }
}
```

### W3C Design Tokens Format
The emerging standard for design token interoperability:
```json
{
  "$schema": "https://design-tokens.org/draft-2024-06/",
  "color": {
    "primary": {
      "$value": "#3B82F6",
      "$type": "color"
    }
  }
}
```

### Tools
| Tool | Purpose |
|---|---|
| [Style Dictionary](https://amzn.github.io/style-dictionary/) | Token transformation pipeline |
| [Tokens Studio](https://tokens.studio/) | Figma plugin for token management |
| [Diez](https://diez.org/) | Design system compiler |
| [Theo](https://github.com/cypress-io/theo) | Token pipeline by Cypress |
| [Panda CSS](https://panda-css.com/) | CSS-in-JS with token support |
| [Tailwind CSS](https://tailwindcss.com/) | Utility-first with token config |

## Token Naming Conventions

### Rules
1. **Use kebab-case:** `--color-primary` not `--colorPrimary`
2. **Semantic over visual:** `--color-text-primary` not `--color-dark-gray`
3. **Tier prefix:** `--color-`, `--space-`, `--font-`, `--shadow-`, `--radius-`
4. **Scale suffix:** `--color-blue-500` (50-900 scale)
5. **State suffix:** `--color-primary-hover`, `--color-primary-active`
6. **No abbreviations:** `--color-background` not `--color-bg` (in semantic layer)

## Implementation Strategy

### 1. Start Small
- Define color, spacing, and typography tokens first
- Add shadow, radius, and z-index next
- Add component tokens last

### 2. Migrate Gradually
- Replace hardcoded values with tokens over time
- Use linting to catch hardcoded values
- Don't do a big-bang migration

### 3. Document
- Every token should have a description
- Show examples of where each token is used
- Provide a visual token catalog

### 4. Version
- Version your token definitions
- Communicate breaking changes
- Consider backward compatibility
