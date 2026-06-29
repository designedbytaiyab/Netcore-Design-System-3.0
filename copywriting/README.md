# Copywriting skill (`copywriting/`)

Self-contained Netcorian copywriting skill. Install **`copywriting/SKILL.md`** separately from the visual design skill at repo root.

## Folder structure

```
copywriting/
├── SKILL.md           ← Install this file for copywriting (/copy trigger)
├── README.md          ← This file
├── spec.md            ← Full copywriting spec (companion to ../design-system.md)
└── references/
    ├── voice.md       ← Netcorian voice, tone, principles
    ├── rules.md       ← Person, tense, case, no em dashes
    ├── patterns.md    ← Buttons, errors, empty states, modals, nudges
    ├── workflows.md   ← Draft + pre-ship checklists
    └── templates.md   ← Feature, wizard, release note templates
```

## Triggers

| Type | Examples |
|---|---|
| Commands | `/copy` · `/netcorian` · `/ux-writing` |
| User says | "write copy", "UX writing", "button label", "error message", "empty state", "in our voice", "Netcorian", "review this copy" |

## Pair with visual skill

| Task | Load |
|---|---|
| UI layout, colours, components | Root `SKILL.md` (`/ds`) |
| UI strings, voice, microcopy | `copywriting/SKILL.md` (`/copy`) |
| Both | Load both skills |
