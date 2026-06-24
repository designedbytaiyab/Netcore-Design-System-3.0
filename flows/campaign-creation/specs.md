# Campaign Creation Flow — Prototype Specs

Reference images: `assets/screens/campaign-creation/` (01 through 10)
Figma nodes: `flows/campaign-creation/figma-nodes.md`

Build this as a single React app with client-side routing between screens. Every screen should feel like the real Netcore product — not a wireframe.

---

## Flow Structure

```
Campaign Home
    → [CREATE button] → Campaign Type Selection (modal)
        → [Engage with users] → Campaign Channel Selection (modal)
            → [Any channel card] → Campaign Setup (full page, stepper starts)
                → [NEXT] → Audience
                    → [NEXT] → Content
                        → [NEXT] → Schedule
                            → [NEXT] → Preview
                                → [SCHEDULE button] → back to Campaign Home
```

---

## Screen 1 — Campaign Home
**Image:** `assets/screens/campaign-creation/01-home.png`
**Interactions:**
- CREATE button (top right) → opens Screen 2 as right-side modal panel
- Table rows are clickable (navigate to setup for that campaign)
- Status chips are display-only

---

## Screen 2 — Campaign Type Selection
**Image:** `assets/screens/campaign-creation/02-type-selection.png`
**Layout:** Right-side modal panel, 840px wide, slides in from right
**Interactions:**
- Click anywhere outside panel → closes modal, back to Screen 1
- × button → closes modal
- "Engage with users" card → navigates to Screen 3 (replaces this modal)
- Other cards → show "Coming soon" toast for prototype purposes

---

## Screen 3 — Campaign Channel Selection
**Image:** `assets/screens/campaign-creation/03-channel-selection.png`
**Layout:** Right-side modal panel, 1136px wide
**Interactions:**
- Any channel card (Email / SMS / WhatsApp / Push / RCS etc.) → closes modal, navigates to Screen 4
- × button → back to Screen 2
- RCS card shows "New" badge — still clickable

---

## Screen 4 — Campaign Setup (Step 1 of 5)
**Image:** `assets/screens/campaign-creation/04-setup.png`
**Layout:** Full page — top bar with stepper + form + right summary panel (350px)
**Stepper:** Step 1 (Setup) active, steps 2–5 inactive
**Interactions:**
- Campaign Name field → typing updates the summary panel in real time
- Tags field → add/remove tags
- Conversion Goal toggle → show/hide sub-fields
- GA Tracking toggle → show/hide UTM fields
- SAVE DRAFT button → shows success toast "Draft saved"
- NEXT button → navigates to Screen 5

---

## Screen 5 — Audience (Step 2 of 5)
**Image:** `assets/screens/campaign-creation/05-audience.png`
**Stepper:** Step 2 active, step 1 completed (checkmark)
**Interactions:**
- Segment selection → selecting a segment updates the summary panel
- BACK → Screen 4
- NEXT → Screen 7 (Content)

---

## Screen 6 — Audience with Filters (Step 2 expanded)
**Image:** `assets/screens/campaign-creation/06-audience-filters.png`
**Note:** This is Screen 5 with filters applied — render as the expanded state when a segment with conditions is selected

---

## Screen 7 — Content / Template Gallery (Step 3 of 5)
**Image:** `assets/screens/campaign-creation/07-content.png`
**Stepper:** Step 3 active
**Interactions:**
- Clicking a template card → selects it, navigates to Screen 8
- BACK → Screen 5

---

## Screen 8 — Content with Template Selected (Step 3 selected)
**Image:** `assets/screens/campaign-creation/08-content-selected.png`
**Interactions:**
- Selected template is highlighted
- NEXT → Screen 9 (Schedule)
- BACK → Screen 7

---

## Screen 9 — Schedule (Step 4 of 5)
**Image:** `assets/screens/campaign-creation/09-schedule.png`
**Stepper:** Step 4 active
**Interactions:**
- Frequency Cap toggle → show/hide warning box below it
- Send now / Send later / Slice & send / Optimize radio group → selecting each shows different sub-content
- SAVE DRAFT → success toast
- NEXT → Screen 10 (Preview)
- BACK → Screen 8

---

## Screen 10 — Preview (Step 5 of 5)
**Image:** `assets/screens/campaign-creation/10-preview.png`
**Stepper:** Step 5 active, steps 1–4 completed
**Interactions:**
- SCHEDULE button → shows success toast "Campaign scheduled successfully", then navigates back to Screen 1 after 2 seconds
- SAVE DRAFT → success toast
- BACK → Screen 9

---

## Shared Chrome

### Top Bar (all screens 4–10)
- Height: 60px
- Left: ← back arrow + campaign name (editable in-place)
- Center: 5-step stepper — active step filled cobalt, completed steps show checkmark, upcoming steps grey
- Right: SAVE DRAFT (secondary button, 125×34px) + SCHEDULE / NEXT (primary button, 106×34px)

### Summary Panel (all screens 4–10)
- Width: 350px, fixed right side
- Shows: Campaign Name, Tags, Conversion Goal, GA Tracking
- Updates in real time as the user fills in each step

### Stepper State Rules
| Step | Active | Completed | Upcoming |
|---|---|---|---|
| Icon | Filled cobalt circle | Cobalt checkmark | Grey outline circle |
| Label | Cobalt text | Grey text | Grey text |
| Connector | Cobalt line | Cobalt line | Grey line |

---

## Prototype Rules

- Keep all navigation client-side — no page reloads
- Modal panels slide in from the right (300ms ease-out)
- Success toasts appear bottom-right, auto-dismiss after 3 seconds
- Use the design system tokens from `references/tokens.md` for all styling
- Every screen must match the reference image — if something is unclear, call the Figma node for that screen
- Do not invent any screen that isn't documented here
