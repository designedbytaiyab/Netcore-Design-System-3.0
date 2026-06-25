# UCE — Unified Content Editor · Interaction Specs

**Status:** Placeholder — to be filled once `designedbytaiyab` has collaborator access on `aim-infinity/uce-email`

**Source repo:** `https://github.com/aim-infinity/uce-email.git`

---

## What UCE is

UCE is Netcore's drag-and-drop email template builder. Marketers use it to build email content — text, images, buttons, product widgets, dynamic blocks — inside a 3-panel editor.

**Where it lives in the product:** Content > Email > Create New Template → choose "Unified editor"

---

## Editor Layout

```
┌─────────────────────────────────────────────────────────┐
│  Top bar — template name, save, preview, send test      │
├──────────────┬──────────────────────┬───────────────────┤
│  LEFT PANEL  │       CANVAS         │   RIGHT PANEL     │
│              │                      │                   │
│  Layouts     │  Drag-and-drop       │  General tab      │
│  Elements    │  workspace           │  Style tab        │
│  Widgets     │                      │                   │
│  Saved       │  Hover block →       │  (per selected    │
│  Blocks      │  Add/Copy/Delete/    │   element)        │
│              │  Save toolbar        │                   │
└──────────────┴──────────────────────┴───────────────────┘
```

---

## Screens / Views

> To be documented with exact dimensions, component names, and interaction rules once repo access is confirmed.

| Screen | Description | Status |
|---|---|---|
| Template list | Entry point — all saved templates | Pending |
| New template modal | Name, category, editor type selection | Pending |
| Editor — empty canvas | Fresh 3-panel editor state | Pending |
| Editor — element selected | Right panel shows element properties | Pending |
| Editor — mobile view | Mobile breakpoint preview mode | Pending |
| Dynamic block rule builder | Visibility rule configuration panel | Pending |
| Product widget config | Dynamic/static product selection | Pending |
| Saved blocks modal | Save block with type + name | Pending |
| Image editor panel | Crop, resize, filters, annotate | Pending |
| AMP email editor | Interactive email mode | Pending |
| Auto-save restore drawer | Two-version restore UI | Pending |

---

## Key Interactions

> To be filled with exact click targets, state changes, and transition rules.

### Adding an element
1. User drags element from left panel onto canvas
2. Element lands at drop position with default size
3. Right panel switches to show that element's properties
4. General tab active by default

### Configuring dynamic visibility
1. Select block on canvas
2. Toggle "Dynamic visibility" ON in right panel
3. Rule builder appears — attribute + operator + value
4. AND/OR logic chain for multiple conditions
5. OR: paste custom visibility code directly

### Saving a block
1. Hover block on canvas → star icon appears
2. Click star → Save block modal opens
3. Select type: Header / Body / Footer / Other
4. Enter name (alphanumeric, underscore, hyphen, spaces)
5. Save → block appears in Saved Blocks section of left panel

---

## Constraints

- Layout width options: 500px / 600px / 700px (700px recommended)
- Max image size: 1.2 MB (PNG, JPEG, JPG, GIF)
- Max products per row in Product Widget: 10
- Product attributes configurable: up to 7
- Social link icons: up to 16
- Auto-save: Email channel only, requires account-level flag
- Image editor: Desktop view only (disabled in mobile view)
- Dynamic visibility: avoid `$`, `"`, `/` in attribute values
- Product widget: if dynamic rule references deleted feed → email dropped in journey

---

## How to add to this file

When repo access is confirmed:
1. Read the source files in `aim-infinity/uce-email`
2. Add exact screen dimensions, component file paths, and prop names per screen row above
3. Fill in interaction rules with real state machine detail
4. Remove "Pending" labels as each screen is documented
