# Netcore Design System — Installation

## What this installs

- CSS custom properties (tokens) for all colours, typography, spacing, radius, and shadows
- Manrope font loaded from Google Fonts
- Base component styles for Input, Button, Badge, Card, Toggle, Alert
- Hard rules that prevent common AI generation failures (dark inputs, wrong radius, green toggles)

## Stack

React + Tailwind CSS. All tokens are CSS custom properties in `:root` and map to Tailwind config.

## Setup steps

1. Add to `index.css`:
   - Import Manrope: `@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@300;400;500;600;700&display=swap');`
   - Paste the full `:root` block from `SKILL.md`

2. Add to `tailwind.config.ts`:
```ts
theme: {
  extend: {
    fontFamily: { sans: ['Manrope', 'system-ui', 'sans-serif'] },
    colors: {
      brand: { DEFAULT: '#2F68E5', hover: '#4F7EF0', active: '#1F51BE' },
      page: '#F4F8FF',
      surface: '#FFFFFF',
    },
    borderRadius: { DEFAULT: '8px', lg: '12px', pill: '9999px' },
  }
}
```

3. Load `SKILL.md` in your AI assistant (Lovable, Claude) to activate the `/ds` trigger.

## Design system reference

Parent system: [Untitled UI v2.0 Figma](https://www.figma.com/design/CjXAv82xiIZH2gABXfbHxB)
Full token spec: `design-system.md` in this repo
