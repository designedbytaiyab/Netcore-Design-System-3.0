# UCE — Figma Node IDs

**Figma File:** [Unified Content Editor (UCE)](https://www.figma.com/design/bssMLRjbn4bEGHsqSJnIpU/Unified-Content-Editor--UCE-)
**File ID:** `bssMLRjbn4bEGHsqSJnIpU`

> This file covers both Email UCE and In-App Message UCE.

---

## Email UCE — Editor Screens

| Screen | Node ID | Dimensions | Figma Link |
|---|---|---|---|
| UCE Editor — Logo element selected (light logo) | `9354:245278` | 1440 × 800 | [Open](https://www.figma.com/design/bssMLRjbn4bEGHsqSJnIpU/Unified-Content-Editor--UCE-?node-id=9354-245278) |
| UCE Editor — Logo element selected (white/inverse logo) | `9367:248946` | 1440 × 800 | [Open](https://www.figma.com/design/bssMLRjbn4bEGHsqSJnIpU/Unified-Content-Editor--UCE-?node-id=9367-248946) |

**What these show:**
- Full 3-panel editor layout: L1 nav (48px) + L2 panel (265px) + Canvas + RHS panel (311px)
- Header bar: back arrow, campaign name ("Campaign name : Test_01"), "Editing in focused view" label, Save Draft + Preview buttons
- Canvas: element selected with selection handles
- RHS panel: General tab active — "Select logo" (URL input), "Configure" (text fields), "Logo size" (slider), "Opacity" (slider)
- Top toolbar: zoom controls (1:1 view), undo/redo, desktop/mobile toggle

---

## RSS Feed Widget — UCE

| Screen | Node ID | Dimensions | Figma Link |
|---|---|---|---|
| RSS Feed widget — empty state (no URL added) | `14798:92` | 1440 × 800 | [Open](https://www.figma.com/design/bssMLRjbn4bEGHsqSJnIpU/Unified-Content-Editor--UCE-?node-id=14798-92) |
| RSS Feed widget — URL input state | `14804:454` | 1440 × 800 | [Open](https://www.figma.com/design/bssMLRjbn4bEGHsqSJnIpU/Unified-Content-Editor--UCE-?node-id=14804-454) |
| RSS Feed widget — URL entered/configured state | `14806:781` | 1440 × 800 | [Open](https://www.figma.com/design/bssMLRjbn4bEGHsqSJnIpU/Unified-Content-Editor--UCE-?node-id=14806-781) |

**What these show:**
- Canvas: RSS Feed block selected, empty state shows icon + "RSS Feed" heading + "Add an RSS feed URL to fetch articles and display them in your email" + CTA button
- L2 panel left: Widgets section — Spin wheel, Jackpot, Quiz, Accordion, Carousel, Cart abandon, Polls, Timer, Coupon
- RHS panel: "RSS feed" breadcrumb header, "RSS Source" section with "RSS feed URL" text field input, Preview + Fetch articles buttons
- States: empty → URL input → URL configured (with radio options for article display)
- Breadcrumb at RHS top: Widget type options → RSS feed

---

## In-App Message UCE — Template Listing

| Screen | Node ID | Dimensions | Figma Link |
|---|---|---|---|
| In-app template listing — System templates tab | `4851:69594` | 1440 × 900 | [Open](https://www.figma.com/design/bssMLRjbn4bEGHsqSJnIpU/Unified-Content-Editor--UCE-?node-id=4851-69594) |
| In-app template listing — My templates tab | `4851:69845` | 1440 × 900 | [Open](https://www.figma.com/design/bssMLRjbn4bEGHsqSJnIpU/Unified-Content-Editor--UCE-?node-id=4851-69845) |

**What these show:**
- Page title: "In-app message templates"
- Tab toggle: System templates | My templates
- "Start from scratch" section — 5 template type cards: Sticky header, Sticky footer, Cover, Interstitial, Half-interstitial
- Filter bar: Date, Contacts dropdowns + Search + Grid/List view toggle
- Template grid: cards grouped by type (Sticky header, Sticky footer, Half-interstitial, Interstitial, Cover)
- My templates tab: cards show "Editor" or "HTML" type badges
- L2 left nav: "In-app message" item highlighted

---

## In-App Message UCE — Editor (Sticky Header)

| Screen | Node ID | Dimensions | Figma Link |
|---|---|---|---|
| In-app editor — Sticky header template edit | `4851:77482` | 1440 × 800 | [Open](https://www.figma.com/design/bssMLRjbn4bEGHsqSJnIpU/Unified-Content-Editor--UCE-?node-id=4851-77482) |

**What this shows:**
- Header: template name "Cart_Abandonment_Fes" (editable), "Sticky header" label chip, Settings / Undo / Save Draft / Publish buttons
- Canvas (BLUE AREA): sticky header preview — "FLASH SALE / Prebook at Rs.1,000..." with CTA button + close icon
- RHS panel has two states shown (both visible in frame):
  - **Simple state:** Transitions (dropdown), Message overlay (color picker), Overlay Opacity (slider)
  - **Full state:** Size (Width %, Min height %), Position (X/Y grid picker + custom inputs), Transitions, Message overlay, Overlay Opacity

---

## DLS Component Nodes (reusable across UCE)

| Component | Node ID (DLS file) | Notes |
|---|---|---|
| Primary button | Map from `GTAOKrmqHr65sLErXRivA6` | `atom/buttons` used throughout UCE frames |
| Input / Text field | Map from `GTAOKrmqHr65sLErXRivA6` | `atom/Text Field` used in RHS property panels |
| Toggle / Switch | Map from `GTAOKrmqHr65sLErXRivA6` | `atom/Switches` used in show/hide toggles |
| Breadcrumb | Map from `GTAOKrmqHr65sLErXRivA6` | Used in RHS panel header |
| Navigation tab | Map from `GTAOKrmqHr65sLErXRivA6` | `molecule/Navigation Tab Toggle Text State` |

---

## How to add more nodes

1. Open the Figma file, select the frame
2. Right-click → Copy link → extract `node-id` from URL
3. Add to the correct section table above
4. Note the frame name from metadata (use `get_metadata` if unsure)
5. Update `specs.md` if new screen reveals new interaction rules
