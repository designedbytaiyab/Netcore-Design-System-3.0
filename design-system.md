# Design System — Complete Reference
> Feed this file to Lovable, Claude, or any AI codegen tool to generate UI that follows this design system exactly.  
> **Parent system:** [Untitled UI v2.0 — FREE Figma UI kit](https://www.figma.com/design/CjXAv82xiIZH2gABXfbHxB/%E2%9D%96-Untitled-UI-%E2%80%93-FREE-Figma-UI-kit-and-design-system-v2.0--Community-) — inherit component anatomy, states, spacing, and interaction patterns from Untitled UI; apply our token overrides below.  
> Last updated: 2026-06-10

---

## 0. Stack & Tooling Decisions

| Decision | Choice | Reason |
|---|---|---|
| **Parent reference** | [Untitled UI v2.0 Figma](https://www.figma.com/design/CjXAv82xiIZH2gABXfbHxB/%E2%9D%96-Untitled-UI-%E2%80%93-FREE-Figma-UI-kit-and-design-system-v2.0--Community-) | Component structure, states, and layout patterns inherit from Untitled UI; we override tokens only |
| Font family | Manrope only — no secondary font | Replaces Untitled UI's Inter; same weight range |
| Colour model | OKLCH-generated, exported as hex | Perceptually uniform scales; Figma doesn't support OKLCH natively yet |
| Contrast standard | WCAG 2.1 AA minimum, AAA preferred | Accessibility-first; tertiary text is large-text AA only |
| Border radius | **8px** universal on all interactive components | Matches Untitled UI; no mixing 6px / 8px |
| Theme | **Light mode only** | Dark mode deferred — never auto-apply dark fills |
| Preview | `npx serve -l 3456 palette` | Static HTML palette reference |

### 0.1 Untitled UI inheritance model

**How to build any component:**
1. Open the matching Untitled UI Figma component (Buttons, Input field, Toggle, Badge, etc.)
2. Copy its anatomy: sizes, padding, states, icon slots, label placement
3. Swap Untitled UI tokens for our semantic tokens using the mapping table below
4. Never invent layout or state patterns — if Untitled UI has it, we have it

**Token override mapping (Untitled UI → ours):**

| Untitled UI token | Our token | Notes |
|---|---|---|
| Inter | Manrope | All typography |
| Brand / Primary blue | `#2F68E5` (blue-600) | Buttons, links, focus, toggle-on |
| Gray neutrals (active UI) | Cool-tinted gray scale (§2.1) | Borders, page bg, body text |
| Gray neutrals (disabled UI) | Untitled neutral disabled set (§2.3) | Disabled fills/borders only — see Figma ref |
| Warning yellow scale | §2.1 Warning Yellow | Same hue family as Untitled UI amber-yellow |
| Success green scale | §2.1 Success Green | Aligned to Untitled UI |
| Error red scale | §2.1 Error Red | Aligned to Untitled UI |
| Side nav dark | `#291E30` | Netcore-specific — not in Untitled UI |

**Figma anchor nodes (Untitled UI file):**

| Component | Node | Use for |
|---|---|---|
| Input field — disabled | [9644:7782](https://www.figma.com/design/CjXAv82xiIZH2gABXfbHxB?node-id=9644-7782) | Disabled field bg, border, shadow |
| Buttons, alerts, toggles | Browse matching Untitled UI page | Anatomy + state variants |

### 0.5 AI generation rules (READ FIRST)

> Hard rules for Lovable, Claude, Cursor, and any CLI agent generating UI from this file.

**What we are building:** Netcore marketing-automation SaaS — campaign wizards, audience tools, email builders, analytics dashboards. Light-mode enterprise UI. Not a marketing landing page, not a dark-theme app.

**Mode:** Light mode only. No `prefers-color-scheme: dark`. No dark input backgrounds. No charcoal form fields.

**Stack default:** React + Tailwind. Paste the `:root` block from §8 before writing components. Load Manrope from Google Fonts.

**Inheritance order:**
1. Untitled UI Figma component (structure + states)
2. This file's semantic tokens (colours, type)
3. §6 / §12 CSS blocks (copy verbatim — do not paraphrase into shadcn defaults)

**Inputs (most common failure — enforce strictly):**
```css
background: #FFFFFF;   /* bg/surface — NEVER dark/charcoal */
color: #17173A;        /* txt/primary */
border: 1px solid #D9D9E8;  /* border/default */
border-radius: 8px;
```
Disabled inputs use §2.3 disabled tokens (`#FAFAFA` bg, `#D4D4D4` border) — still light, never dark.

**Forbidden (will be rejected):**
- Dark input backgrounds (`gray-800`, `gray-900`, `bg-muted` in dark context, `#252530`, `#181820`)
- Green toggles or green "on" states — brand blue `#2F68E5` only
- `border-radius: 6px` on buttons, inputs, or cards — use **8px**
- shadcn/ui `Input` or `Button` without overriding to match §6 CSS
- Inventing colours outside §2.2–2.6 semantic tokens
- Using `txt/tertiary` for body copy or labels (placeholder text only)
- Using `txt/disabled` on interactive/enabled elements

**Text colour rules (quick reference):**

| Token | Use for | Never use for |
|---|---|---|
| `txt/primary` `#17173A` | Headings, labels, body, input values | Placeholders, disabled text |
| `txt/secondary` `#6F6F8D` | Descriptions, helper text, secondary labels | Headings, placeholders |
| `txt/tertiary` `#9494AE` | Placeholder text, table headers, captions ≥18px | Body copy, form labels |
| `txt/disabled` `#9494AE` | Disabled field values, disabled button labels | Any enabled/interactive text |
| `txt/brand` `#2F68E5` | Links, active nav, focused labels | Body paragraphs |
| `txt/error` `#C0201A` | Error messages, error helpers | Non-error UI |
| `txt/warning` `#B54708` | Warning messages, warning helpers | Non-warning UI |
| `txt/success` `#079455` | Success messages, confirmations | Non-success UI |

---

## 1. Typography System

### 1.1 Font

```
font-family: 'Manrope', system-ui, -apple-system, sans-serif;
```

**Weights in use:**

| Token | CSS value |
|---|---|
| L (Light) | 300 |
| R (Regular) | 400 |
| M (Medium) | 500 |
| SB (SemiBold) | 600 |
| B (Bold) | 700 |

### 1.2 Type Scale (ascending — smallest to largest)

Naming convention: `{Group}-{Size}/{Weight}`  
Example: `Body-mid-M/SB` = Body-mid group, Medium size, SemiBold weight

| Token Group | Size Name | px | Line Height | Letter Spacing | Available Weights |
|---|---|---|---|---|---|
| Caption | Caption-S | 10px | 18px | −1 (−0.01em) | L · M · SB · B |
| Caption | Caption-M | 12px | 20px | −1 (−0.01em) | L · M · SB · B |
| Body-mid | Body-mid-S | 13px | 21px | −1 (−0.01em) | L · R · M · SB · B |
| Body-mid | **Body-mid-M** ← primary | **14px** | **22px** | −1 (−0.01em) | L · R · M · SB · B |
| Body-mid | Body-mid-L | 15px | 23px | −1 (−0.01em) | L · R · M · SB · B |
| Body-lg | Body-lg-MD | 16px | 24px | −1 (−0.01em) | L · R · M · SB · B |
| Body-lg | Body-lg-LG | 18px | 26px | −1 (−0.01em) | L · R · M · SB · B |
| Heading | Heading-H3 | 20px | 30px | −1 (−0.01em) | L · R · M · SB · B |
| Heading | Heading-H2 | 22px | 32px | −1 (−0.01em) | L · R · M · SB · B |
| Heading | Heading-H1 | 24px | 34px | −1 (−0.01em) | L · R · M · SB · B |
| Display | Display-S | 28px | 38px | −1.5 (−0.015em) | L · R · M · SB · B |
| Display | Display-M | 32px | 42px | −1.5 (−0.015em) | L · R · M · SB · B |
| Display | Display-L | 36px | 46px | −1.5 (−0.015em) | L · R · M · SB · B |
| Display | Display-XL | 40px | 50px | −1.5 (−0.015em) | L · R · M · SB · B |

**Line height formula:**
- Display & Heading groups: `font-size + 10px`
- Body & Caption groups: `font-size + 8px`

**Letter spacing:**
- Display group only: `−1.5px` (−0.015em)
- All other groups: `−1px` (−0.01em)

### 1.3 Semantic Text Tokens

These are the two named semantic tokens used throughout the system:

| Semantic Token | Resolves to | CSS |
|---|---|---|
| `Primary-txt/M` | Body-mid-M / Medium | `font-size: 14px; line-height: 22px; font-weight: 500; letter-spacing: -0.01em` |
| `Secondary-txt/M` | Body-mid-S / Medium | `font-size: 13px; line-height: 21px; font-weight: 500; letter-spacing: -0.01em` |

### 1.4 Typography Usage Rules

- **Headings (H1–H3):** Use SemiBold (SB) or Bold (B) weights; never Light for headings
- **Body copy (default):** `Body-mid-M/M` (14px / Medium) — this is the base reading size
- **Secondary/support text:** `Body-mid-S/M` (13px / Medium)
- **Captions, labels, status:** Caption group; M or SB weight
- **Display text (hero, marketing):** Display group; SB or B weight
- **Disabled text:** Any size, always `txt/disabled` (`#9494AE`) — never `txt/tertiary` or `txt/primary` on disabled elements
- **Never use L (Light) weight** for text smaller than 14px — poor legibility at small sizes

### 1.5 Figma text style naming

Pattern: `{Group}/{Size-name}/{Weight}` — e.g. `Body-mid/Body-mid-M/SB`, `Caption/Caption-M/M`.  
Use `-` for spaces in size names. No numeric prefixes (breaks CSS variable naming).  
Mirror Untitled UI's text style groups; swap Inter → Manrope in our Figma file.

---

## 2. Colour System

All colours generated using the OKLCH colour model for perceptual uniformity, then converted to hex for compatibility. Each scale has 12 steps: 25 / 50 / 100 / 200 / 300 / 400 / 500 / 600 / 700 / 800 / 900 / 950.

### 2.1 Primitive Colour Scales

#### Primary Blue — H 265° (Brand colour)

| Step | Hex | Usage |
|---|---|---|
| 25 | `#F6F8FF` | Page/section background tint |
| 50 | `#EDF1FF` | Subtle highlight, badge bg |
| 100 | `#D8E6FF` | Hover fill light |
| 200 | `#AEBFFF` | Decorative accent |
| 300 | `#7EA4FF` | Decorative, illustration |
| 400 | `#4F7EF0` | Hover state |
| 500 | `#3B71E8` | Interactive default |
| **600** | **`#2F68E5`** | **Brand colour — primary buttons, links, focus rings** |
| 700 | `#1F51BE` | Pressed/active state |
| 800 | `#143A92` | Dark accent |
| 900 | `#0A2667` | Very dark |
| 950 | `#07184A` | Near-black |

#### Neutral Gray — H 250° (Cool-tinted)

| Step | Hex | Usage |
|---|---|---|
| 25 | `#FAFBFF` | App background |
| 50 | `#F5F6FA` | Card background, subtle fills — **not** disabled fields (use `bg/disabled` §2.3) |
| 100 | `#EBEBF5` | Border light, divider |
| 200 | `#D9D9E8` | Default input border |
| 300 | `#BBBBC8` | Placeholder, tertiary border |
| 400 | `#919198` | Disabled text, placeholder |
| 500 | `#6B6B78` | Supporting text |
| 600 | `#50505D` | Body text secondary |
| 700 | `#383845` | Body text |
| 800 | `#252530` | Strong body |
| 900 | `#181820` | Near black |
| 950 | `#101018` | Darkest |

#### Error Red — H 20°

| Step | Hex | Usage |
|---|---|---|
| 25 | `#FFF5F5` | Error section bg |
| 50 | `#FFEBE8` | Error badge bg, error field bg |
| 100 | `#FECDCC` | Light error |
| 200 | `#FDA29B` | Decorative |
| 300 | `#F97066` | Icon |
| 400 | `#F04438` | Strong visual |
| 500 | `#D92D20` | Error hover |
| **600** | **`#C0201A`** | **Error default — border, icon, text on white** |
| 700 | `#9A1B14` | Error pressed |
| 800 | `#771510` | Dark |
| 900 | `#540D0A` | Very dark |
| 950 | `#3C0807` | Near-black |

#### Warning Yellow — H 38–45° (Untitled UI hue, lighter variant)

> **Decision:** Warning follows the Untitled UI amber-yellow hue (H≈38–45°). This is the universal "caution" colour in design systems — warm golden-yellow at bright steps, readable dark amber at text/border steps. It is visually distinct from the brand logo orange (#FC5E02, H=22°) and from Error Red. The palette is intentionally lighter and more saturated than the previous H=90° pure-yellow attempt.

| Step | Hex | Usage |
|---|---|---|
| 25 | `#FFFDF5` | Warning section bg |
| 50 | `#FFFAEB` | Warning badge bg, field bg |
| 100 | `#FEF0C7` | Light yellow |
| 200 | `#FEDF89` | Decorative |
| 300 | `#FEC84B` | **Warning visual indicator — icon, highlight** |
| 400 | `#FDB022` | Warning icon (darker variant) |
| 500 | `#F79009` | Warning golden |
| **600** | **`#DC6803`** | **Warning border token** (3.4:1 on white — WCAG non-text ✅) |
| **700** | **`#B54708`** | **Warning text token** (5.1:1 on white — AA ✅) |
| 800 | `#93370D` | Dark warning |
| 900 | `#7A2E0E` | Very dark |
| 950 | `#4E1D09` | Near-black |

#### Success Green — H 155°

| Step | Hex | Usage |
|---|---|---|
| 25 | `#F6FEF9` | Success section bg |
| 50 | `#ECFDF3` | Success badge bg, field bg |
| 100 | `#DCFAE6` | Light |
| 200 | `#ABEFC6` | Decorative |
| 300 | `#75E0A7` | Icon light |
| 400 | `#47CD89` | Success visual |
| 500 | `#17B26A` | Success hover |
| **600** | **`#079455`** | **Success default — border, icon, text on white** |
| 700 | `#067647` | Success pressed |
| 800 | `#085D3A` | Dark |
| 900 | `#053321` | Very dark |
| 950 | `#022113` | Near-black |

#### Accent Orange — H 38° (Logo colour)

> **Note:** This is the brand logo colour only. Do not use for warning states. Use Primary Blue for CTAs; Accent Orange is a decorative/branding colour.

| Step | Hex | Usage |
|---|---|---|
| 25 | `#FFF8F5` | Subtle bg |
| 50 | `#FFF0E8` | Tint |
| 100 | `#FFDCCC` | Light |
| 200 | `#FFB799` | Decorative |
| 300 | `#FF8C62` | Illustration |
| 400 | `#FF6E35` | Bright accent |
| 500 | `#FF620C` | Near-logo |
| **600** | **`#FC5E02`** | **Logo colour** |
| 700 | `#D44600` | Dark accent |
| 800 | `#A63300` | Darker |
| 900 | `#762200` | Very dark |
| 950 | `#511600` | Near-black |

### 2.2 Semantic Text Colour Tokens

These are the only text colour tokens to use in components. Never reference primitive steps directly in component code.

| Token | Hex | WCAG on `#F4F8FF` | Use for |
|---|---|---|---|
| `txt/primary` | `#17173A` | AAA · 14.6:1 | Headings, body text, labels, all default text |
| `txt/secondary` | `#6F6F8D` | AA · 4.56:1 | Descriptions, helper text, secondary labels |
| `txt/tertiary` | `#9494AE` | Large-text AA · 3.0:1 | Placeholder text only, table column headers, captions ≥18px — never body copy or labels |
| `txt/disabled` | `#9494AE` | Exempt | Disabled field values and disabled button labels — tuned softer than Untitled UI `#A3A3A3` (see §2.3) |
| `txt/brand` | `#2F68E5` | AA · 5.0:1 | Links, brand-coloured labels, active nav items |
| `txt/error` | `#C0201A` | AA · 6.1:1 | Error messages, error field labels |
| `txt/warning` | `#B54708` | AA · 5.1:1 | Warning messages, warning field labels |
| `txt/success` | `#079455` | AA · 6.8:1 | Success messages, confirmation text |
| `txt/inverse` | `#FFFFFF` | AAA · 16:1 on `#291E30` | Text on the dark side nav |

### 2.3 Disabled tokens (Untitled UI base + our text tune)

> **Source:** [Untitled UI — Input field disabled](https://www.figma.com/design/CjXAv82xiIZH2gABXfbHxB?node-id=9644-7782) (`9644:7782`).  
> Untitled UI uses `#A3A3A3` for disabled text and `opacity-50` on some components — both read too strong at small sizes. We keep Untitled fills/borders/shadows; disabled **text** uses our `txt/disabled` (`#9494AE`) for softer hierarchy.

| Token | Hex | Untitled UI equivalent | Use for |
|---|---|---|---|
| `bg/disabled` | `#FAFAFA` | Neutral/50 | Disabled input bg, disabled secondary button bg |
| `bg/disabled-subtle` | `#F5F5F5` | Neutral/100 | Disabled primary button bg |
| `txt/disabled` | `#9494AE` | Neutral/400 `#A3A3A3` (tuned down) | Disabled input values, disabled button labels, disabled icons |
| `border/disabled` | `#D4D4D4` | Neutral/300 | Disabled input/button borders |
| `shadow/disabled` | `0 1px 2px rgba(0,0,0,0.05)` | Shadow/xs | Disabled inputs only — matches Untitled UI |

**Disabled button rules (inherits Untitled UI button disabled anatomy):**

| Variant | Background | Border | Text | Cursor |
|---|---|---|---|---|
| Primary disabled | `#F5F5F5` | none | `#9494AE` | `not-allowed` |
| Secondary disabled | `#FAFAFA` | `1px #D4D4D4` | `#9494AE` | `not-allowed` |
| Ghost disabled | transparent | none | `#9494AE` | `not-allowed` |
| Destructive disabled | `#F5F5F5` | none | `#9494AE` | `not-allowed` |
| Warning disabled | `#FAFAFA` | `1px #D4D4D4` | `#9494AE` | `not-allowed` |

Do **not** use brand blue, error red, or warning amber on disabled buttons.

### 2.4 Background & Surface Tokens

| Token | Hex | Use for |
|---|---|---|
| `bg/page` | `#F4F8FF` | Main page background |
| `bg/surface` | `#FFFFFF` | Cards, modals, dropdowns, **enabled inputs** |
| `bg/subtle` | `#FAFBFF` | Nested sections, table rows |
| `bg/nav` | `#291E30` | Side navigation |
| `bg/error` | `#FFF5F5` | Error state field background |
| `bg/warning` | `#FFFAEB` | Warning state field background |
| `bg/success` | `#F6FEF9` | Success state field background |

### 2.5 Border Tokens

| Token | Hex | Use for |
|---|---|---|
| `border/default` | `#D9D9E8` | Default input, card borders |
| `border/hover` | `#9898B0` | Input hover state |
| `border/focus` | `#2F68E5` | Input focused state (1.5px) |
| `border/error` | `#C0201A` | Error field border (1.5px) |
| `border/warning` | `#DC6803` | Warning field border (1.5px) |
| `border/success` | `#079455` | Success field border (1.5px) |
| `border/disabled` | `#D4D4D4` | Disabled field/button border (Untitled UI Neutral/300) |

### 2.6 Focus Ring Tokens (box-shadow)

All focus rings use 4px spread, 0 blur, no offset.

| Token | CSS value | Use for |
|---|---|---|
| `ring/brand` | `0 0 0 4px rgba(47,104,229,0.15)` | Default focus |
| `ring/error` | `0 0 0 4px rgba(192,32,26,0.15)` | Error focused |
| `ring/warning` | `0 0 0 4px rgba(220,104,3,0.15)` | Warning focused |
| `ring/success` | `0 0 0 4px rgba(7,148,85,0.15)` | Success focused |

---

## 3. Spacing & Layout

| Token | Value | Use |
|---|---|---|
| `spacing/xs` | 4px | Icon padding, tight gaps |
| `spacing/sm` | 8px | Inner component padding |
| `spacing/md` | 12px | Component padding |
| `spacing/lg` | 16px | Section padding |
| `spacing/xl` | 24px | Card padding |
| `spacing/2xl` | 32px | Section gaps |
| `spacing/3xl` | 48px | Page padding |

---

## 4. Border Radius

> **Decision: 8px everywhere. No exceptions for interactive components.**

| Token | Value | Use |
|---|---|---|
| `radius/sm` | 4px | Very small elements only (tooltip arrows, small chips) |
| `radius/md` | 6px | Inner elements within components (progress bar, avatar placeholder) |
| `radius/default` | **8px** | **All interactive components: inputs, cards, buttons, modals, dropdowns, badges** |
| `radius/lg` | 12px | Large containers, modals |
| `radius/xl` | 16px | Feature cards |
| `radius/pill` | 999px | Pill-shaped badges, toggle tracks |

---

## 5. Shadows

| Token | CSS value | Use |
|---|---|---|
| `shadow/xs` | `0 1px 2px rgba(23,23,58,0.08)` | Subtle cards, hover lift |
| `shadow/sm` | `0 1px 3px rgba(23,23,58,0.10)` | Cards, dropdowns |
| `shadow/md` | `0 4px 8px rgba(23,23,58,0.12)` | Modals, popovers |
| `shadow/lg` | `0 8px 24px rgba(23,23,58,0.14)` | Dialogs |

---

## 6. Components

> All components inherit anatomy and state variants from [Untitled UI Figma](https://www.figma.com/design/CjXAv82xiIZH2gABXfbHxB). CSS below applies our token overrides.

### 6.1 Input Field

> Untitled UI ref: Input field component set. Disabled ref: node `9644:7782`.

**Base CSS:**
```css
.input {
  font-family: 'Manrope', sans-serif;
  font-size: 13px;          /* Body-mid-S */
  font-weight: 500;         /* M */
  line-height: 21px;
  letter-spacing: -0.01em;
  border-radius: 8px;
  padding: 9px 12px;
  width: 100%;
  border: 1px solid #D9D9E8;
  background: #FFFFFF;
  color: #17173A;
  outline: none;
  transition: border-color 0.15s, box-shadow 0.15s;
}
```

**Label CSS:**
```css
.input-label {
  font-size: 12px;          /* Caption-M */
  font-weight: 600;         /* SB */
  line-height: 20px;
  letter-spacing: -0.01em;
  color: #17173A;           /* txt/primary */
  display: block;
  margin-bottom: 6px;       /* Untitled UI label gap */
}
```

**Helper text CSS:**
```css
.input-helper {
  font-size: 10px;
  color: #6F6F8D;
  margin-top: 5px;
}
```

**State variants:**

| State | Border | Background | Box Shadow | Label colour | Helper colour |
|---|---|---|---|---|---|
| Default | `1px #D9D9E8` | `#FFFFFF` | none | `#17173A` | `#6F6F8D` |
| Hover | `1px #9898B0` | `#F6F8FF` | `shadow/xs` | `#17173A` | `#6F6F8D` |
| Focused | `1.5px #2F68E5` | `#FFFFFF` | `ring/brand` | `#2F68E5` | `#6F6F8D` |
| Disabled | `1px #D4D4D4` | `#FAFAFA` | `shadow/disabled` | `#17173A` at reduced emphasis — label stays primary; value text `#9494AE` | `#9494AE` |
| Error | `1.5px #C0201A` | `#FFF5F5` | none | `#17173A` | `#C0201A` |
| Error Focused | `1.5px #C0201A` | `#FFFFFF` | `ring/error` | `#C0201A` | `#C0201A` |
| Warning | `1.5px #DC6803` | `#FFFAEB` | none | `#17173A` | `#B54708` |
| Warning Focused | `1.5px #DC6803` | `#FFFFFF` | `ring/warning` | `#B54708` | `#B54708` |
| Success | `1.5px #079455` | `#F6FEF9` | none | `#17173A` | `#079455` |
| Success Focused | `1.5px #079455` | `#FFFFFF` | `ring/success` | `#079455` | `#079455` |

**Placeholder text colour:** `#9494AE` (txt/tertiary) — only use on inputs, never for body text.

### 6.2 Button

> Untitled UI ref: Buttons component set (primary, secondary, tertiary, destructive, warning).

**Primary Button:**
```css
.btn-primary {
  background: #2F68E5;
  color: #FFFFFF;
  border: none;
  border-radius: 8px;
  font-size: 14px;
  font-weight: 600;
  padding: 10px 20px;
  cursor: pointer;
  transition: background 0.15s;
}
.btn-primary:hover   { background: #4F7EF0; }
.btn-primary:active  { background: #1F51BE; }
.btn-primary:focus   { box-shadow: 0 0 0 4px rgba(47,104,229,0.15); outline: none; }
.btn-primary:disabled { background: #F5F5F5; color: #9494AE; cursor: not-allowed; pointer-events: none; }
```

**Secondary Button (outlined):**
```css
.btn-secondary {
  background: #FFFFFF;
  color: #2F68E5;
  border: 1.5px solid #2F68E5;
  border-radius: 8px;
  font-size: 14px;
  font-weight: 600;
  padding: 10px 20px;
  cursor: pointer;
}
.btn-secondary:hover  { background: #EDF1FF; }
.btn-secondary:active { background: #D8E6FF; border-color: #1F51BE; color: #1F51BE; }
.btn-secondary:disabled { background: #FAFAFA; border-color: #D4D4D4; color: #9494AE; cursor: not-allowed; pointer-events: none; }
```

**Ghost Button:**
```css
.btn-ghost {
  background: transparent;
  color: #2F68E5;
  border: none;
  border-radius: 8px;
  font-size: 14px;
  font-weight: 600;
  padding: 10px 20px;
  cursor: pointer;
}
.btn-ghost:hover  { background: #EDF1FF; }
.btn-ghost:active { background: #D8E6FF; }
.btn-ghost:disabled { color: #9494AE; cursor: not-allowed; pointer-events: none; }
```

**Destructive Button:**
```css
.btn-destructive {
  background: #C0201A;
  color: #FFFFFF;
  border: none;
  border-radius: 8px;
  font-size: 14px;
  font-weight: 600;
  padding: 10px 20px;
  cursor: pointer;
}
.btn-destructive:hover  { background: #D92D20; }
.btn-destructive:active { background: #9A1B14; }
.btn-destructive:disabled { background: #F5F5F5; color: #9494AE; cursor: not-allowed; pointer-events: none; }
```

**Warning Button (Untitled UI warning secondary):**
```css
.btn-warning {
  background: #FFFFFF;
  color: #B54708;           /* txt/warning */
  border: 1.5px solid #DC6803;  /* border/warning */
  border-radius: 8px;
  font-size: 14px;
  font-weight: 600;
  padding: 10px 20px;
  cursor: pointer;
}
.btn-warning:hover  { background: #FFFAEB; border-color: #B54708; }
.btn-warning:active { background: #FEF0C7; border-color: #93370D; color: #93370D; }
.btn-warning:focus  { box-shadow: 0 0 0 4px rgba(220,104,3,0.15); outline: none; }
.btn-warning:disabled { background: #FAFAFA; border-color: #D4D4D4; color: #9494AE; cursor: not-allowed; pointer-events: none; }
```

**Button sizes:**

| Size | Font | Padding | Height |
|---|---|---|---|
| sm | 12px / SB | 6px 14px | 32px |
| md (default) | 14px / SB | 10px 20px | 40px |
| lg | 16px / SB | 12px 24px | 48px |

### 6.3 Badge / Tag

**Base styles:**
```css
.badge {
  display: inline-block;
  font-size: 12px;
  font-weight: 600;
  padding: 5px 14px;
  border-radius: 8px;           /* default rounded */
}
.badge-pill {
  border-radius: 999px;         /* pill variant */
}
```

**Colour variants:**

| Variant | Background | Text colour |
|---|---|---|
| Brand | `#EDF1FF` | `#1F51BE` |
| Error | `#FFEBE8` | `#9A1B14` |
| Warning | `#FFFAEB` | `#B54708` |
| Success | `#ECFDF3` | `#067647` |
| Neutral | `#EBEBF5` | `#383845` |
| Accent | `#FFF0E8` | `#A63300` |

**Badge sizes:**

| Size | Font | Padding |
|---|---|---|
| sm | 10px / SB | 2px 8px |
| md (default) | 12px / SB | 5px 14px |
| lg | 13px / SB | 6px 16px |

### 6.4 Card

```css
.card {
  background: #FFFFFF;
  border-radius: 8px;
  border: 1px solid #EBEBF5;
  box-shadow: 0 1px 3px rgba(23,23,58,0.10);
  padding: 24px;
}
.card:hover {
  box-shadow: 0 4px 8px rgba(23,23,58,0.12);
  border-color: #D9D9E8;
}
```

**Card variants:**

| Variant | Description |
|---|---|
| Default | White bg, light border, sm shadow |
| Elevated | White bg, no border, md shadow |
| Outlined | White bg, heavier border (200 step), no shadow |
| Filled | `bg/subtle` (#FAFBFF), border, no shadow |

### 6.5 Navigation (Side Nav)

```css
.sidenav {
  background: #291E30;
  width: 240px;
  min-height: 100vh;
  padding: 16px 12px;
}
.sidenav-item {
  color: rgba(255,255,255,0.70);
  font-size: 14px;
  font-weight: 500;
  padding: 10px 12px;
  border-radius: 8px;
  cursor: pointer;
  transition: background 0.1s;
}
.sidenav-item:hover {
  background: rgba(255,255,255,0.08);
  color: #FFFFFF;
}
.sidenav-item.active {
  background: rgba(47,104,229,0.25);
  color: #FFFFFF;
}
```

### 6.6 Modal / Dialog

```css
.modal-overlay {
  background: rgba(23,23,58,0.5);
  position: fixed; inset: 0;
  display: flex; align-items: center; justify-content: center;
}
.modal {
  background: #FFFFFF;
  border-radius: 12px;
  box-shadow: 0 8px 24px rgba(23,23,58,0.14);
  padding: 32px;
  max-width: 520px;
  width: calc(100% - 32px);
}
.modal-title {
  font-size: 18px;
  font-weight: 700;
  color: #17173A;
  margin-bottom: 8px;
}
.modal-body {
  font-size: 14px;
  color: #6F6F8D;
  line-height: 22px;
}
.modal-actions {
  display: flex;
  gap: 12px;
  justify-content: flex-end;
  margin-top: 24px;
}
```

### 6.7 Toast / Alert

**Alert base:**
```css
.alert {
  border-radius: 8px;
  padding: 14px 16px;
  font-size: 14px;
  font-weight: 500;
  display: flex;
  gap: 12px;
  align-items: flex-start;
}
```

| Variant | Background | Border-left | Icon + Text colour |
|---|---|---|---|
| Info | `#EDF1FF` | `3px solid #2F68E5` | `#1F51BE` |
| Error | `#FFEBE8` | `3px solid #C0201A` | `#9A1B14` |
| Warning | `#FFFAEB` | `3px solid #DC6803` | `#B54708` |
| Success | `#ECFDF3` | `3px solid #079455` | `#067647` |

### 6.8 Table

```css
.table { width: 100%; border-collapse: collapse; }
.table th {
  font-size: 12px; font-weight: 600;   /* Caption-M/SB */
  text-transform: uppercase; letter-spacing: 0.07em;
  color: #9494AE;                      /* txt/tertiary — table headers only */
  background: #FAFBFF;
  padding: 10px 16px;
  text-align: left;
  border-bottom: 1px solid #EBEBF5;
}
.table td {
  font-size: 14px; color: #17173A;
  padding: 14px 16px;
  border-bottom: 1px solid #EBEBF5;
}
.table tr:hover td { background: #F6F8FF; }
.table tr:last-child td { border-bottom: none; }
```

### 6.9 Checkbox & Radio

```css
.checkbox {
  width: 16px; height: 16px;
  border: 1.5px solid #D9D9E8;
  border-radius: 4px;
  background: #FFFFFF;
  cursor: pointer;
  transition: border-color 0.1s, background 0.1s;
}
.checkbox:hover   { border-color: #9898B0; }
.checkbox:checked { background: #2F68E5; border-color: #2F68E5; }
.checkbox:focus   { box-shadow: 0 0 0 4px rgba(47,104,229,0.15); outline: none; }
.checkbox:disabled { background: #FAFAFA; border-color: #D4D4D4; cursor: not-allowed; opacity: 1; }

.radio {
  /* Same as checkbox but border-radius: 50% */
  border-radius: 50%;
}
```

### 6.10 Select / Dropdown

Inherits all Input Field states. Additional:
```css
.select {
  appearance: none;
  background-image: url("chevron-down-icon");
  background-repeat: no-repeat;
  background-position: right 12px center;
  padding-right: 36px;
  cursor: pointer;
}
```

---

## 7. Responsive Breakpoints

| Breakpoint | Min-width | Description |
|---|---|---|
| `xs` | 0px | Mobile portrait |
| `sm` | 480px | Mobile landscape |
| `md` | 768px | Tablet |
| `lg` | 1024px | Desktop |
| `xl` | 1280px | Wide desktop |
| `2xl` | 1440px | Max layout width |

**Max content width:** `1400px` (centred with `margin: 0 auto`)

**Grid columns:**

| Breakpoint | Columns | Gutter |
|---|---|---|
| xs | 4 | 16px |
| sm | 4 | 16px |
| md | 8 | 20px |
| lg | 12 | 24px |
| xl | 12 | 24px |

---

## 8. CSS Custom Properties (Full Token Sheet)

Paste this in your global CSS `:root {}` block:

```css
:root {
  /* === TYPEFACE === */
  --font-family: 'Manrope', system-ui, -apple-system, sans-serif;

  /* === TYPE SCALE === */
  --text-caption-s:   10px; --lh-caption-s:   18px;
  --text-caption-m:   12px; --lh-caption-m:   20px;
  --text-body-mid-s:  13px; --lh-body-mid-s:  21px;
  --text-body-mid-m:  14px; --lh-body-mid-m:  22px;
  --text-body-mid-l:  15px; --lh-body-mid-l:  23px;
  --text-body-lg-md:  16px; --lh-body-lg-md:  24px;
  --text-body-lg-lg:  18px; --lh-body-lg-lg:  26px;
  --text-heading-h3:  20px; --lh-heading-h3:  30px;
  --text-heading-h2:  22px; --lh-heading-h2:  32px;
  --text-heading-h1:  24px; --lh-heading-h1:  34px;
  --text-display-s:   28px; --lh-display-s:   38px;
  --text-display-m:   32px; --lh-display-m:   42px;
  --text-display-l:   36px; --lh-display-l:   46px;
  --text-display-xl:  40px; --lh-display-xl:  50px;

  --ls-body:    -0.01em;
  --ls-display: -0.015em;

  /* === FONT WEIGHTS === */
  --fw-light:    300;
  --fw-regular:  400;
  --fw-medium:   500;
  --fw-semibold: 600;
  --fw-bold:     700;

  /* === PRIMARY BLUE === */
  --blue-25:  #F6F8FF; --blue-50:  #EDF1FF; --blue-100: #D8E6FF;
  --blue-200: #AEBFFF; --blue-300: #7EA4FF; --blue-400: #4F7EF0;
  --blue-500: #3B71E8; --blue-600: #2F68E5; --blue-700: #1F51BE;
  --blue-800: #143A92; --blue-900: #0A2667; --blue-950: #07184A;

  /* === NEUTRAL GRAY === */
  --gray-25:  #FAFBFF; --gray-50:  #F5F6FA; --gray-100: #EBEBF5;
  --gray-200: #D9D9E8; --gray-300: #BBBBC8; --gray-400: #919198;
  --gray-500: #6B6B78; --gray-600: #50505D; --gray-700: #383845;
  --gray-800: #252530; --gray-900: #181820; --gray-950: #101018;

  /* === ERROR RED === */
  --red-25:  #FFF5F5; --red-50:  #FFEBE8; --red-100: #FECDCC;
  --red-200: #FDA29B; --red-300: #F97066; --red-400: #F04438;
  --red-500: #D92D20; --red-600: #C0201A; --red-700: #9A1B14;
  --red-800: #771510; --red-900: #540D0A; --red-950: #3C0807;

  /* === WARNING YELLOW (Untitled UI hue H=38-45°) === */
  --yellow-25:  #FFFDF5; --yellow-50:  #FFFAEB; --yellow-100: #FEF0C7;
  --yellow-200: #FEDF89; --yellow-300: #FEC84B; --yellow-400: #FDB022;
  --yellow-500: #F79009; --yellow-600: #DC6803; --yellow-700: #B54708;
  --yellow-800: #93370D; --yellow-900: #7A2E0E; --yellow-950: #4E1D09;

  /* === SUCCESS GREEN === */
  --green-25:  #F6FEF9; --green-50:  #ECFDF3; --green-100: #DCFAE6;
  --green-200: #ABEFC6; --green-300: #75E0A7; --green-400: #47CD89;
  --green-500: #17B26A; --green-600: #079455; --green-700: #067647;
  --green-800: #085D3A; --green-900: #053321; --green-950: #022113;

  /* === ACCENT ORANGE === */
  --orange-25:  #FFF8F5; --orange-50:  #FFF0E8; --orange-100: #FFDCCC;
  --orange-200: #FFB799; --orange-300: #FF8C62; --orange-400: #FF6E35;
  --orange-500: #FF620C; --orange-600: #FC5E02; --orange-700: #D44600;
  --orange-800: #A63300; --orange-900: #762200; --orange-950: #511600;

  /* === SEMANTIC TEXT TOKENS === */
  --txt-primary:   #17173A;
  --txt-secondary: #6F6F8D;
  --txt-tertiary:  #9494AE;
  --txt-disabled:  #9494AE;
  --txt-brand:     #2F68E5;
  --txt-error:     #C0201A;
  --txt-warning:   #B54708;
  --txt-success:   #079455;
  --txt-inverse:   #FFFFFF;

  /* === BACKGROUNDS === */
  --bg-page:    #F4F8FF;
  --bg-surface: #FFFFFF;
  --bg-subtle:  #FAFBFF;
  --bg-nav:     #291E30;
  --bg-error:   #FFF5F5;
  --bg-warning: #FFFAEB;
  --bg-success: #F6FEF9;

  /* === BORDERS === */
  --border-default: #D9D9E8;
  --border-hover:   #9898B0;
  --border-focus:   #2F68E5;
  --border-error:   #C0201A;
  --border-warning: #DC6803;
  --border-success: #079455;
  --border-disabled:#D4D4D4;

  /* === DISABLED (Untitled UI base — §2.3) === */
  --bg-disabled:        #FAFAFA;
  --bg-disabled-subtle: #F5F5F5;
  --shadow-disabled:    0 1px 2px rgba(0,0,0,0.05);

  /* === FOCUS RINGS === */
  --ring-brand:   0 0 0 4px rgba(47,104,229,0.15);
  --ring-error:   0 0 0 4px rgba(192,32,26,0.15);
  --ring-warning: 0 0 0 4px rgba(220,104,3,0.15);
  --ring-success: 0 0 0 4px rgba(7,148,85,0.15);

  /* === SHADOWS === */
  --shadow-xs: 0 1px 2px rgba(23,23,58,0.08);
  --shadow-sm: 0 1px 3px rgba(23,23,58,0.10);
  --shadow-md: 0 4px 8px rgba(23,23,58,0.12);
  --shadow-lg: 0 8px 24px rgba(23,23,58,0.14);

  /* === RADIUS === */
  --radius-sm:      4px;
  --radius-md:      6px;
  --radius-default: 8px;
  --radius-lg:      12px;
  --radius-xl:      16px;
  --radius-pill:    999px;

  /* === SPACING === */
  --space-xs:  4px;
  --space-sm:  8px;
  --space-md:  12px;
  --space-lg:  16px;
  --space-xl:  24px;
  --space-2xl: 32px;
  --space-3xl: 48px;
}
```

---

## 9. Decision Log

| # | Decision | Rationale |
|---|---|---|
| 1 | Single typeface: Manrope | Avoids secondary font management; Manrope's 5 weights cover all weight needs |
| 2 | No numeric prefixes in style names | Numeric prefixes (01-, 02-) break CSS variable naming conventions and look messy in code |
| 3 | No `link` as a type style | Link behaviour is a colour token decision, not a font style variant |
| 4 | Caption group gets only 4 weights (L·M·SB·B), no R | Regular weight at 10–12px is indistinguishable from Medium; R excluded for simplicity |
| 5 | Line height: font+10 for Display/Heading, font+8 for Body/Caption | Tighter line height for display keeps headlines compact; looser for body aids readability |
| 6 | Letter spacing: −1.5 for Display, −1 for all other groups | Display text benefits from tighter tracking at large sizes; moderate negative tracking for body reduces spaced-out appearance |
| 7 | Type scale groups: Display-XL(28–40), Heading(24–20), Body-lg(18–16), Body-mid(15–14–13), Caption(12–10) | Mirrors Untitled UI structure; groups reflect semantic use, not just size |
| 8 | Primary semantic style: Body-mid-M/M (14px Medium) | 14px is the primary reading size; Medium weight balances legibility and formality |
| 9 | Secondary semantic style: Body-mid-S/M (13px Medium) | One step smaller for supporting content |
| 10 | OKLCH for colour generation | Perceptually uniform — hue, chroma, and lightness steps feel consistent across the scale |
| 11 | Brand primary: #2F68E5 (Blue-600) | Customer-confirmed existing brand colour |
| 12 | Side nav: #291E30 | Customer-confirmed existing dark purple nav |
| 13 | Logo/accent: #FC5E02 (Orange-600) | Customer-confirmed logo orange; separate from warning colour |
| 14 | Text colour system: 3-tier primary/secondary/tertiary | Tiered hierarchy for visual weight management; tertiary (#9494AE) is intentionally at the AA floor for large text only |
| 15 | txt/secondary (#6F6F8D) is deliberately at AA floor (4.56:1) | The existing brand secondary text colour was #6F6F8D; we matched it and verified it just clears AA |
| 16 | Warning hue follows Untitled UI amber-yellow (H=38–45°) | Initial H=90° pure yellow looked too neon/citrus and did not feel "warning." Untitled UI's proven amber-yellow palette reads as caution universally, distinguishes clearly from brand orange (H=22°) and error red |
| 17 | Warning border = step 600 (#DC6803), text = step 700 (#B54708) | Bright yellow at 300–400 is the visual identity (icons, fills). Border 600 passes WCAG non-text 3:1 (3.4:1). Text 700 passes WCAG AA on white (5.1:1). Badge text uses 700 on 50 bg for AA |
| 21 | Component states: Default · Hover · Focused · Selected · Error · Disabled | Six universal states cover all interactive component behaviours. "Selected" replaces "Active" to be semantically accurate — a selected item stays selected, whereas "active" implies momentary press |
| 22 | Atomic Design structure in Figma | Atoms → Molecules → Organisms → Templates → Pages maps directly to how Figma components are composed. Atoms are individual tokens-bound components; Molecules combine atoms; Organisms are full sections |
| 23 | Command palette deferred to Untitled UI command menu | Inherit when needed; not specced locally yet |
| 18 | Border radius = 8px universal | Consistent radius across all interactive components; no mixing 6px/8px; 8px is the design intent |
| 19 | Focus ring: 4px spread, 15% opacity brand colour | Visible but non-jarring focus indicator; meets WCAG 2.4.11 (enhanced focus appearance) |
| 20 | Placeholder text uses txt/tertiary (#9494AE) | Placeholder is intentionally low-hierarchy; not a substitute for labels |
| 24 | Untitled UI as parent reference | Component anatomy, states, and disabled fills inherit from Untitled UI Figma; we override brand colour, font, cool neutrals, and disabled text tune |
| 25 | Disabled fills from Untitled UI Neutral/50–300 | bg `#FAFAFA`, border `#D4D4D4`, shadow-xs — ref node 9644:7782; text tuned to `#9494AE` (softer than Untitled `#A3A3A3`) |
| 26 | Warning alerts/buttons use Untitled UI amber-yellow | bg `#FFFAEB`, border `#DC6803`, text `#B54708` — replaces ad-hoc `#FEF9C3` / `#A16207` values |

---

## 10. Atomic Design Architecture

Follows Brad Frost's Atomic Design. **Component anatomy comes from Untitled UI**; our Figma file mirrors Untitled UI's page structure with token overrides applied.

```
ATOMS      → Button, Input, Badge, Checkbox, Toggle, Avatar, Icon, Divider, Tag
MOLECULES  → Input Group, Search Bar, Form Field, Dropdown Item, Nav Item, Toast
ORGANISMS  → Navigation Bar, Side Nav, Form, Data Table, Card Grid, Modal, Tabs
TEMPLATES  → Dashboard Layout, Settings Page, Login Page
PAGES      → (empty — generated per project)
```

**Figma reference anchor:** Use [Untitled UI v2.0](https://www.figma.com/design/CjXAv82xiIZH2gABXfbHxB) as the source component library. Our file `Test-Design-system-3.0` applies Manrope + Netcore tokens on top — same page order as Untitled UI Foundations → Atoms → Molecules → Organisms.

---

## 11. Universal Component States

Every interactive component in this design system implements these **6 states**. Build all 6 — never skip one.

| State | Trigger | Visual signal |
|---|---|---|
| **Default** | No interaction | Base appearance — border `#D9D9E8`, bg white, text `#17173A` |
| **Hover** | Mouse over | Border `#9898B0`, bg `#F6F8FF`, `shadow/xs` lift |
| **Focused** | Keyboard focus / click into | Border 1.5px `#2F68E5`, focus ring `ring/brand` (4px spread, 15% opacity) |
| **Selected** | Item is chosen / active | bg `#EDF1FF`, border `#2F68E5`, text `#2F68E5` or `#17173A` |
| **Error** | Validation failure | Border 1.5px `#C0201A`, bg `#FFF5F5`, helper text `#C0201A` |
| **Disabled** | Not interactive | bg `#FAFAFA`, border `#D4D4D4`, text `#9494AE`, `cursor: not-allowed` — Untitled UI fills + our text tune (§2.3) |

> **Selected vs Active:** "Selected" means a persistent chosen state (e.g. a nav item, a tab, a checkbox). "Active" (press/mousedown) is a momentary state — implement it as a darker fill on hover but do not create it as a separate Figma variant unless the component explicitly needs it.

### State CSS helpers

```css
/* Selected */
.is-selected {
  background: #EDF1FF;
  border-color: #2F68E5;
  color: #2F68E5;
}

/* Hover */
.is-hover {
  background: #F6F8FF;
  border-color: #9898B0;
  box-shadow: var(--shadow-xs);
}

/* Focused */
.is-focused {
  border: 1.5px solid #2F68E5;
  box-shadow: var(--ring-brand);
  outline: none;
}

/* Disabled */
.is-disabled {
  background: #FAFAFA;
  border-color: #D4D4D4;
  color: #9494AE;
  box-shadow: 0 1px 2px rgba(0,0,0,0.05);
  pointer-events: none;
  cursor: not-allowed;
}
```

---

## 12. Extended Component Library

> Inherit structure from matching Untitled UI components; apply §6 / §8 token overrides.

### 12.1 Dropdown / Select Menu

```css
/* Trigger button — inherits Input Field states */
.dropdown-trigger {
  border-radius: 8px;
  padding: 9px 36px 9px 12px;
  background: #FFFFFF url("chevron-icon") no-repeat right 12px center;
  border: 1px solid #D9D9E8;
  font-size: 13px; font-weight: 500;
  cursor: pointer;
  width: 100%;
}

/* Menu container */
.dropdown-menu {
  position: absolute;
  top: calc(100% + 4px);
  left: 0; right: 0;
  background: #FFFFFF;
  border: 1px solid #EBEBF5;
  border-radius: 8px;
  box-shadow: var(--shadow-md);
  padding: 4px;
  z-index: 50;
}

/* Menu item */
.dropdown-item {
  padding: 8px 12px;
  border-radius: 6px;
  font-size: 13px; font-weight: 500;
  color: #17173A;
  cursor: pointer;
}
.dropdown-item:hover    { background: #F6F8FF; }
.dropdown-item.selected { background: #EDF1FF; color: #2F68E5; }
.dropdown-item.disabled { color: #9494AE; cursor: not-allowed; }
```

**Dropdown states:** Default · Hover (trigger) · Open · Item Hover · Item Selected · Disabled

### 12.2 Toggle / Switch

> Untitled UI ref: Toggle component. **On state = brand blue `#2F68E5` — never green.**

```css
.toggle {
  width: 44px; height: 24px;
  background: #D9D9E8;
  border-radius: 999px;
  position: relative;
  cursor: pointer;
  transition: background 0.15s;
  border: none;
}
.toggle::after {
  content: '';
  position: absolute;
  top: 2px; left: 2px;
  width: 20px; height: 20px;
  background: #FFFFFF;
  border-radius: 50%;
  box-shadow: var(--shadow-xs);
  transition: transform 0.15s;
}
.toggle.on            { background: #2F68E5; }
.toggle.on::after     { transform: translateX(20px); }
.toggle:focus         { box-shadow: var(--ring-brand); outline: none; }
.toggle.disabled      { opacity: 0.4; cursor: not-allowed; }
```

**Toggle states:** Off-Default · Off-Hover · Off-Focused · On-Default · On-Hover · On-Focused · Disabled-Off · Disabled-On

**Sizes:**

| Size | Track | Thumb |
|---|---|---|
| sm | 32×18px | 14px |
| md (default) | 44×24px | 20px |
| lg | 56×32px | 28px |

### 12.3 Tabs

```css
.tabs { display: flex; border-bottom: 1px solid #EBEBF5; gap: 0; }

.tab {
  padding: 10px 16px;
  font-size: 14px; font-weight: 600;
  color: #6F6F8D;
  cursor: pointer;
  border-bottom: 2px solid transparent;
  margin-bottom: -1px;
  transition: color 0.1s, border-color 0.1s;
  white-space: nowrap;
}
.tab:hover   { color: #17173A; }
.tab.active  {
  color: #2F68E5;
  border-bottom-color: #2F68E5;
}
.tab.disabled { color: #9494AE; cursor: not-allowed; }

/* Pill variant */
.tabs-pill { gap: 4px; border-bottom: none; background: #F5F6FA; border-radius: 8px; padding: 4px; }
.tabs-pill .tab {
  border-radius: 6px;
  border-bottom: none;
  margin-bottom: 0;
}
.tabs-pill .tab.active { background: #FFFFFF; color: #17173A; box-shadow: var(--shadow-xs); }
```

**Tab states:** Default · Hover · Active/Selected · Disabled · (with count badge variant)

### 12.4 Tooltip

```css
.tooltip {
  position: absolute;
  background: #17173A;
  color: #FFFFFF;
  font-size: 12px; font-weight: 500;
  padding: 6px 10px;
  border-radius: 6px;
  white-space: nowrap;
  pointer-events: none;
  z-index: 100;
  box-shadow: var(--shadow-sm);
}
/* Arrow */
.tooltip::after {
  content: '';
  position: absolute;
  border: 5px solid transparent;
}
/* Top tooltip arrow */
.tooltip.top::after {
  top: 100%; left: 50%; transform: translateX(-50%);
  border-top-color: #17173A;
}
```

**Tooltip variants:** Top · Bottom · Left · Right  
**Tooltip sizes:** sm (no title, label only) · md (title + body)  
**Trigger:** appears on hover/focus, disappears on blur/mouseout. Delay: 300ms show, 0ms hide.

### 12.5 Breadcrumb

```css
.breadcrumb {
  display: flex; align-items: center; gap: 6px;
  font-size: 13px; font-weight: 500;
  flex-wrap: wrap;
}
.breadcrumb-item { color: #6F6F8D; }
.breadcrumb-item a { color: #6F6F8D; text-decoration: none; }
.breadcrumb-item a:hover { color: #2F68E5; }
.breadcrumb-item.current { color: #17173A; font-weight: 600; }
.breadcrumb-sep { color: #BBBBC8; font-size: 12px; }
```

### 12.6 Pagination

```css
.pagination { display: flex; align-items: center; gap: 4px; }

.page-btn {
  min-width: 36px; height: 36px;
  display: flex; align-items: center; justify-content: center;
  border-radius: 8px;
  font-size: 13px; font-weight: 600;
  color: #6F6F8D;
  border: 1px solid transparent;
  cursor: pointer;
  transition: background 0.1s;
}
.page-btn:hover    { background: #F5F6FA; color: #17173A; }
.page-btn.active   { background: #EDF1FF; color: #2F68E5; border-color: #2F68E5; }
.page-btn.disabled { color: #9494AE; cursor: not-allowed; }

/* Prev/Next buttons */
.page-nav {
  padding: 0 12px;
  font-size: 13px; font-weight: 600;
  color: #17173A;
  border: 1px solid #D9D9E8;
  border-radius: 8px;
}
```

### 12.7 Avatar

```css
.avatar {
  border-radius: 50%;
  object-fit: cover;
  background: #EDF1FF;
  color: #2F68E5;
  font-weight: 700;
  display: flex; align-items: center; justify-content: center;
}

/* Sizes */
.avatar-xs  { width: 24px;  height: 24px;  font-size: 10px; }
.avatar-sm  { width: 32px;  height: 32px;  font-size: 12px; }
.avatar-md  { width: 40px;  height: 40px;  font-size: 14px; }
.avatar-lg  { width: 48px;  height: 48px;  font-size: 16px; }
.avatar-xl  { width: 64px;  height: 64px;  font-size: 20px; }

/* Status dot */
.avatar-status {
  width: 10px; height: 10px;
  border-radius: 50%;
  border: 2px solid #FFFFFF;
  position: absolute; bottom: 0; right: 0;
}
.status-online  { background: #079455; }
.status-away    { background: #F79009; }
.status-offline { background: #9494AE; }
```

**Avatar variants:** Image · Initials · Icon placeholder  
**Avatar group:** Overlapping stack (−8px margin), max 5 visible + "+N" overflow badge

### 12.8 Accordion

```css
.accordion { border: 1px solid #EBEBF5; border-radius: 8px; overflow: hidden; }
.accordion + .accordion { margin-top: 8px; }

.accordion-trigger {
  width: 100%;
  display: flex; align-items: center; justify-content: space-between;
  padding: 16px;
  font-size: 14px; font-weight: 600; color: #17173A;
  background: #FFFFFF;
  border: none; cursor: pointer;
  transition: background 0.1s;
}
.accordion-trigger:hover  { background: #FAFBFF; }
.accordion-trigger.open   { border-bottom: 1px solid #EBEBF5; }
.accordion-chevron        { transition: transform 0.2s; color: #6F6F8D; }
.accordion-trigger.open .accordion-chevron { transform: rotate(180deg); }

.accordion-content {
  padding: 16px;
  font-size: 14px; line-height: 22px; color: #6F6F8D;
  background: #FFFFFF;
}
```

**Accordion states:** Closed-Default · Closed-Hover · Open · Disabled  
**Accordion variants:** Single open (close others on open) · Multiple open

### 12.9 Stepper / Progress Indicator

```css
.stepper { display: flex; align-items: flex-start; gap: 0; }

.step { flex: 1; display: flex; flex-direction: column; align-items: center; }

.step-circle {
  width: 32px; height: 32px;
  border-radius: 50%;
  border: 2px solid #D9D9E8;
  background: #FFFFFF;
  display: flex; align-items: center; justify-content: center;
  font-size: 13px; font-weight: 700; color: #9494AE;
  position: relative; z-index: 1;
}
.step.completed .step-circle { background: #2F68E5; border-color: #2F68E5; color: #FFFFFF; }
.step.active    .step-circle { border-color: #2F68E5; color: #2F68E5; box-shadow: var(--ring-brand); }
.step.error     .step-circle { border-color: #C0201A; color: #C0201A; }

.step-label {
  font-size: 12px; font-weight: 600; color: #9494AE;
  text-align: center; margin-top: 6px;
}
.step.active .step-label    { color: #2F68E5; }
.step.completed .step-label { color: #17173A; }

/* Connector line */
.step-connector {
  flex: 1; height: 2px;
  background: #D9D9E8;
  margin-top: 15px;
}
.step-connector.completed { background: #2F68E5; }
```

### 12.10 Notification / Toast

```css
.toast {
  display: flex; align-items: flex-start; gap: 12px;
  background: #FFFFFF;
  border: 1px solid #EBEBF5;
  border-radius: 8px;
  padding: 14px 16px;
  box-shadow: var(--shadow-md);
  min-width: 320px; max-width: 480px;
}
.toast-icon  { flex-shrink: 0; margin-top: 1px; }
.toast-title { font-size: 14px; font-weight: 700; color: #17173A; }
.toast-body  { font-size: 13px; color: #6F6F8D; margin-top: 2px; }
.toast-close { margin-left: auto; color: #9494AE; cursor: pointer; padding: 2px; }
.toast-close:hover { color: #17173A; }
```

**Toast variants** (left accent stripe):

| Type | Accent | Icon colour |
|---|---|---|
| Info | `#2F68E5` | Blue |
| Success | `#079455` | Green |
| Warning | `#DC6803` | Amber |
| Error | `#C0201A` | Red |

**Toast positions:** Top-right (default) · Top-center · Bottom-right · Bottom-center  
**Toast auto-dismiss:** 5 seconds (info/success), stays until dismissed (error/warning)

### 12.11 Data Table (extended)

Building on the base table in §6.8:

```css
/* Row selection */
.table tr.selected td { background: #F6F8FF; }

/* Sortable header */
.table th.sortable { cursor: pointer; }
.table th.sortable:hover { color: #17173A; }
.table th.sort-asc::after  { content: ' ↑'; }
.table th.sort-desc::after { content: ' ↓'; }

/* Empty state row */
.table-empty td {
  text-align: center; padding: 48px 16px;
  color: #9494AE; font-size: 14px;
}

/* Row actions (appear on row hover) */
.table tr:hover .row-actions { opacity: 1; }
.row-actions { opacity: 0; transition: opacity 0.1s; }
```

**Table variants:** Basic · Striped · Bordered · Compact · With row selection · With sorting · With pagination

### 12.12 Slider / Range Input

```css
.slider { width: 100%; appearance: none; height: 4px; border-radius: 999px; background: #D9D9E8; outline: none; }
.slider::-webkit-slider-thumb {
  appearance: none;
  width: 20px; height: 20px;
  border-radius: 50%;
  background: #2F68E5;
  border: 2px solid #FFFFFF;
  box-shadow: var(--shadow-sm);
  cursor: pointer;
}
.slider:focus::-webkit-slider-thumb { box-shadow: var(--ring-brand); }
.slider:disabled { opacity: 0.4; cursor: not-allowed; }
```

---

## 13. Command Palette (Ctrl+K)

> Deferred — inherit from Untitled UI Command Menu / Search component when needed. Use modal overlay tokens from §6.6 (`rgba(23,23,58,0.5)` backdrop, `bg/surface` modal, `radius/lg` 12px).

---

## 14. What Remains

| Item | Status | Notes |
|---|---|---|
| Untitled UI → our Figma token sync | 🔲 In progress | Parent: [Untitled UI v2.0](https://www.figma.com/design/CjXAv82xiIZH2gABXfbHxB); our file `Test-Design-system-3.0` |
| Netcore Rebrand reference screens | 🔲 Needs Figma open | File `BLtps2BIkxYLhFtgwty2gg` — nodes 3673:39737, 3671:35786, 4585:37976 |
| Command palette (§13) | 🔲 Deferred | Use Untitled UI command menu when needed |
| Dark mode token set | 🔲 Deferred | Light mode only until specced |
| Data visualisation / chart colours | 🔲 Deferred | Separate session |
| Animation / transition tokens | 🔲 Deferred | Separate session |
| Icon library | 🔲 Deferred | Inherit Untitled UI icon set |
| Empty state illustrations | 🔲 Deferred | Per-section empty states |
