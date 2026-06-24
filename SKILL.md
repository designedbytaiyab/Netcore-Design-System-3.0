---
name: netcore-design-system
description: Apply the Netcore design system for any UI generation. Enforces Manrope font, brand blue #2F68E5, white inputs, 8px radius. Also builds pixel-accurate interactive prototypes from real Netcore screen designs — use when someone asks to prototype, replicate, or build a clickable version of any Netcore flow. CRITICAL — never violate: (1) inputs always white #FFFFFF, (2) font always Manrope, (3) toggles on-state always #2F68E5 blue never green. Trigger on /ds or /design-system commands, and automatically when any request combines a UI action (build, create, add, show, design, make, update, prototype, replicate, clone) with Netcore product vocabulary: campaign, audience, segment, journey, automation, subscriber, contact, broadcast, email template, A/B test, analytics, open rate, CTR, settings, user management, wizard, builder, workflow, push notification, trigger, flow, or any SaaS admin interface.
---

# Netcore Design System

This skill does two things:
1. **Design system enforcement** — applies tokens, typography, and component rules to any UI generation
2. **Prototype generation** — builds interactive, clickable React prototypes from real Netcore screen designs so PMs can walk through real flows

---

## How to handle any request

**If the request is about building / prototyping a specific Netcore flow:**
→ Go to the **Prototype Generation** section below. Load the flow's images first, then specs, then generate.

**If the request is about UCE (User Communication Engine) or the email builder:**
→ Go to the **UCE — Code-First Generation** section below. This flow has a different path depending on which tool you are running in.

**If the request is about styling, tokens, or general UI generation:**
→ Go to the **Design System Rules** section below.

---

## PROTOTYPE GENERATION

### Available Flows

| Flow | Images | Specs | Figma Nodes |
|---|---|---|---|
| Campaign Creation (10 screens) | `assets/screens/campaign-creation/` | `flows/campaign-creation/specs.md` | `flows/campaign-creation/figma-nodes.md` |

> To add a new flow in the future: create `flows/<flow-name>/specs.md` + `figma-nodes.md`, add screenshots to `assets/screens/<flow-name>/`, and add a row to the table above.

### Trigger Keywords → Campaign Creation Flow
Any of these phrases trigger the campaign creation prototype:
`campaign creation flow` · `create a campaign` · `campaign wizard` · `campaign prototype` · `campaign flow` · `build the campaign` · `replicate the campaign` · `campaign type selection` · `campaign channel` · `campaign setup` · `campaign audience` · `campaign content` · `campaign schedule` · `campaign preview`

### Workflow — Prototype Requests

```
1. Identify which screen(s) are needed from the trigger keyword
2. Display the reference image: assets/screens/campaign-creation/0N-screen-name.png
3. Read flows/campaign-creation/specs.md for interaction rules
4. Read flows/campaign-creation/figma-nodes.md for exact dimensions
5. Apply design system tokens from references/tokens.md
6. Generate interactive React code — screens connected, navigation working
7. Verify: does it match the reference image? Are interactions wired?
```

Displaying the image first is not optional — it grounds the output in the real design before any code is written.

### Prototype Quality Standards
- Client-side navigation only — no page reloads between screens
- Modal panels slide in from right (300ms ease-out)
- Stepper updates correctly as the user progresses through each step
- Summary panel updates in real time as the user fills in fields
- Success toasts appear bottom-right, auto-dismiss after 3 seconds
- Every screen must match its reference image — if dimensions are unclear, call the Figma node
- Do not invent any screen or interaction not documented in `flows/campaign-creation/specs.md`

---

## UCE — Code-First Generation

UCE (User Communication Engine) has an existing codebase already built. The goal here is not to generate UI from scratch — it's to read the existing code, understand what's already been built, and use it as the base for any improvements or new screens. This gives PMs the real bare-bones of the feature to ideate on top of.

**Source repo:** `https://github.com/aim-infinity/uce-email.git`

### Trigger Keywords
Any of these phrases trigger the UCE code-first workflow:
`UCE` · `user communication engine` · `UCE email` · `email builder` · `UCE builder` · `improve UCE` · `UCE design` · `UCE prototype` · `UCE flow` · `email campaign builder`

---

### ⚠️ Access is environment-dependent — read this before proceeding

This repo is private. Only **Lovable** has OAuth access to it. Claude Code does not and should not attempt to access it.

---

### PATH A — Running in Lovable (has repo access)

Lovable has the `aim-infinity/uce-email` repo connected. You have full read access to the codebase.

**Workflow:**
```
1. Scan the existing codebase — find all components, pages, and layouts
2. Map what already exists: which screens are built, which components are reusable
3. Display the relevant component files so the user can see the current state
4. Apply DS 3.0 tokens (Manrope, #2F68E5, white inputs) on top of the existing code
5. Extend or improve the design using the existing code as the skeleton
6. Do not rebuild from scratch — reuse what is there
```

When a PM asks to "improve the UCE email builder" or "redesign the UCE flow":
- Read the existing component files first
- Show them what the current code produces
- Then propose improvements on top of it — never replace the whole thing

> File paths and component names will be filled in once repo access is confirmed. A placeholder note will be removed at that point.

---

### PATH B — Running in Claude Code (no repo access)

Claude Code cannot access `aim-infinity/uce-email` — it is a private repo under a different GitHub org.

**Do not attempt to clone or read this repo.**

Instead:
- Tell the user: "UCE code-first generation requires Lovable — the repo is private and only accessible there."
- Fall back to design system rules from `references/tokens.md` and `references/components.md`
- Use DS 3.0 tokens to generate a best-effort UI, clearly labelled as a starting point — not based on the real codebase

---

### When repo access is granted to `designedbytaiyab`

Once access is confirmed, this section will be updated with:
- Exact file paths for key components
- Component inventory (what exists, what's missing)
- Which files to read first for each trigger phrase

---

## DESIGN SYSTEM RULES

Apply these rules to every component, screen, and form. Do not invent values — use what is here.

---

## PRIMARY — Design system rules

### Non-negotiable rules

**Font: Manrope only.**
Add to every project: `@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@300;400;500;600;700&display=swap');`
Never use Inter, system-ui, or Tailwind's default font stack.

**Page and surface colours.**
Page background: `#F4F8FF`. Card background: `#FFFFFF`. Input background: `#FFFFFF`. Never dark backgrounds on any of these.

**Inputs are always white.**
`background: #FFFFFF` on every input, select, textarea. This is the single most common AI generation failure — dark or grey inputs are wrong.

**Brand blue is `#2F68E5`.** Primary buttons, focus rings, active states, links. Never approximate with Tailwind's `blue-500` or `blue-600`.

**Border radius is 8px everywhere.** Buttons, inputs, cards, modals, badges — all 8px. Modal overlay uses 12px. Pills use 999px.

**Toggles: on = `#2F68E5` (blue). Never green.** Green is reserved for success badges and alerts only.

**Disabled states: bg `#FAFAFA`, border `#D4D4D4`, text `#9494AE`.** Never use brand colours on disabled elements.

**Text hierarchy: three tiers only.**
- Primary `#17173A` — headings, labels, values
- Secondary `#6F6F8D` — descriptions, helper text
- Tertiary `#9494AE` — placeholders, table column headers

**Never invent values.** If a colour, size, or spacing value isn't in the token table below, it doesn't belong in the output. Do not approximate with Tailwind utilities like `bg-blue-500` or `text-gray-400`.

---

### Token reference

| Role | Hex |
|---|---|
| Brand blue | `#2F68E5` |
| Brand blue hover | `#4F7EF0` |
| Brand blue active | `#1F51BE` |
| Brand blue subtle | `#EDF1FF` |
| Page background | `#F4F8FF` |
| Card / input background | `#FFFFFF` |
| Text primary | `#17173A` |
| Text secondary | `#6F6F8D` |
| Text tertiary / placeholder | `#9494AE` |
| Border default | `#D9D9E8` |
| Border hover | `#9898B0` |
| Border focus | `#2F68E5` |
| Disabled background | `#FAFAFA` |
| Disabled border | `#D4D4D4` |
| Disabled text | `#9494AE` |
| Error | `#C0201A` |
| Warning border | `#DC6803` |
| Warning text | `#B54708` |
| Success | `#079455` |
| Side nav background | `#291E30` |

Full `:root` block → `references/tokens.md`

---

### Core components — copy these exactly

#### Input
```css
.input {
  background: #FFFFFF;
  border: 1px solid #D9D9E8;
  border-radius: 8px;
  padding: 9px 12px;
  font-family: 'Manrope', sans-serif;
  font-size: 13px;
  font-weight: 500;
  color: #17173A;
  outline: none;
  width: 100%;
}
.input:hover    { border-color: #9898B0; background: #F6F8FF; }
.input:focus    { border: 1.5px solid #2F68E5; box-shadow: 0 0 0 4px rgba(47,104,229,0.15); }
.input:disabled { background: #FAFAFA; border-color: #D4D4D4; color: #9494AE; }
.input::placeholder { color: #9494AE; }

.input-label {
  font-size: 12px; font-weight: 600;
  color: #17173A; display: block; margin-bottom: 6px;
}
```

#### Primary button
```css
.btn-primary {
  background: #2F68E5;
  color: #FFFFFF;
  border: none;
  border-radius: 8px;
  font-family: 'Manrope', sans-serif;
  font-size: 14px;
  font-weight: 600;
  padding: 10px 20px;
  cursor: pointer;
}
.btn-primary:hover    { background: #4F7EF0; }
.btn-primary:active   { background: #1F51BE; }
.btn-primary:disabled { background: #F5F5F5; color: #9494AE; cursor: not-allowed; }
```

#### Secondary button (outlined)
```css
.btn-secondary {
  background: #FFFFFF;
  color: #2F68E5;
  border: 1.5px solid #2F68E5;
  border-radius: 8px;
  font-size: 14px; font-weight: 600;
  padding: 10px 20px; cursor: pointer;
}
.btn-secondary:hover    { background: #EDF1FF; }
.btn-secondary:disabled { background: #FAFAFA; border-color: #D4D4D4; color: #9494AE; }
```

#### Card
```css
.card {
  background: #FFFFFF;
  border: 1px solid #EBEBF5;
  border-radius: 8px;
  box-shadow: 0 1px 3px rgba(23,23,58,0.10);
  padding: 24px;
}
```

#### Badge / status chip

| Variant | Background | Text |
|---|---|---|
| Brand | `#EDF1FF` | `#1F51BE` |
| Success | `#ECFDF3` | `#067647` |
| Warning | `#FFFAEB` | `#B54708` |
| Error | `#FFEBE8` | `#9A1B14` |
| Neutral | `#EBEBF5` | `#383845` |

```css
.badge { font-size: 12px; font-weight: 600; padding: 5px 14px; border-radius: 8px; }
```

#### Toggle / switch
```css
.toggle { width: 44px; height: 24px; background: #D9D9E8; border-radius: 999px; position: relative; cursor: pointer; border: none; }
.toggle::after { content: ''; position: absolute; top: 2px; left: 2px; width: 20px; height: 20px; background: #FFFFFF; border-radius: 50%; }
.toggle.on        { background: #2F68E5; }   /* BLUE — never green */
.toggle.on::after { transform: translateX(20px); }
```

#### Alert / banner
| Type | Background | Left border (3px) | Text |
|---|---|---|---|
| Info | `#EDF1FF` | `#2F68E5` | `#1F51BE` |
| Warning | `#FFFAEB` | `#DC6803` | `#B54708` |
| Error | `#FFEBE8` | `#C0201A` | `#9A1B14` |
| Success | `#ECFDF3` | `#079455` | `#067647` |

---

### Typography

Font: **Manrope** only.

| Use case | Size | Weight | Colour |
|---|---|---|---|
| Page headings | 20–24px | 600 | `#17173A` |
| Body copy | 14px | 500 | `#17173A` |
| Helper / description | 13px | 500 | `#6F6F8D` |
| Input labels | 12px | 600 | `#17173A` |
| Placeholders, table headers | 13px | 500 | `#9494AE` |
| Badges, captions | 10–12px | 600 | (badge variant colour) |

---

## SECONDARY — When to trigger

### Explicit triggers
- `/ds [prompt]` or `/design-system [prompt]`

### Implicit triggers — Netcore product vocabulary
Trigger automatically when a UI request contains any of these words:

**Product:** campaign · journey · automation · audience · segment · subscriber · contact · broadcast · template · trigger · workflow · A/B test

**Channels:** email builder · SMS · push notification · WhatsApp · in-app message

**Analytics:** open rate · CTR · conversion · delivery rate · bounce · engagement · impressions

**UI contexts:** campaign wizard · segment builder · audience filter · user management · invite user · settings page · data table · analytics dashboard

### Does not trigger
- Generic requests with no Netcore context: `"build a landing page"`, `"create a sign-up form"` — too generic
- Informational: `"what is a design system"`, `"explain tokens"` — no UI to build

### PM vocabulary → component mapping
When a PM describes UI in plain language, map it to design system components:

| PM says | Use this |
|---|---|
| `button`, `CTA`, `action` | `btn-primary` (`#2F68E5`) or `btn-secondary` (outlined) |
| `modal`, `popup`, `dialog` | Modal overlay `rgba(23,23,58,0.5)`, card `bg-white rounded-[12px]` |
| `table`, `list view`, `data grid` | Table `th` = tertiary `#9494AE` uppercase, `td` = primary `#17173A`, row hover `#F6F8FF` |
| `input`, `text field`, `form field` | `bg-white border-[#D9D9E8] rounded-[8px]` — never dark bg |
| `tag`, `badge`, `status chip` | Badge token variants only: brand/success/warning/error/neutral |
| `toggle`, `switch` | On = `#2F68E5` blue, Off = `#D9D9E8` — never green |
| `sidebar`, `nav` | bg `#291E30`, items `rgba(255,255,255,0.70)`, active `rgba(47,104,229,0.25)` |
| `cramped` / `more space` | Adjust padding within token scale — never invent pixel values |
| `more rounded` | Step up from `8px` to `12px` — never `rounded-3xl` or custom values |

---

## Reference files

| File | When to read |
|---|---|
| `references/tokens.md` | Before writing `index.css` — full `:root` block |
| `references/components.md` | Input states, all button variants, nav, modal, table |
| `references/extended.md` | Stepper, tabs, pagination, accordion, data table, avatar, slider |

---

## Campaign creation flow

When building any campaign creation screen (Email, WhatsApp, SMS, Push, RCS, or any new channel):

- **Live reference:** https://product-netcore.github.io/campaign-creation-flow/
- **Structure docs:** https://product-netcore.github.io/campaign-creation-flow/#/docs
- **Source repo:** https://github.com/Product-Netcore/campaign-creation-flow

**Precedence:** 3.0 rules win. Mirror the reference for structure and layout; apply 3.0 token overrides below.

| What the reference shows | 3.0 override |
|---|---|
| Font: Nunito Sans | → **Manrope** |
| Next Step bg: `#143F93` | → **`#2F68E5`** |
| Input bg: `#F8F8F8` | → **`#FFFFFF`** (inputs always white) |
| Toggle on: `#00C48C` green | → **`#2F68E5`** blue (toggles on = blue, never green) |
| Active stepper: `#00C48C` green | → **`#2F68E5`** blue |
| Completed stepper: `#00C48C` green | → `#15B079` green |
| Border radius: 6px | → **`8px`** |
| Borders: `#DDE2EE` | → `#D9D9E8` (`var(--border-default)`) |

Do not invent a new layout — copy `CampaignSetupStep.tsx` and change only the fields.
