# netcore-design-system

> "The AI doesn't have bad taste. It just doesn't know yours."

Every time a PM asks Claude or Lovable to build a campaign form, the same thing happens. Inter font. Grey inputs. Green toggles. A border radius that's almost right but isn't. The output looks like a prototype from a different product — because the AI made its own decisions instead of yours.

The frustrating part: you've already made those decisions. The tokens exist. The components are specced. The design system is written down. The AI just doesn't know about it.

**This skill is the bridge.** One file. Install once. And every AI-generated screen — campaign wizards, audience filters, email builders, analytics dashboards, settings pages, data tables — comes out with Manrope, `#2F68E5`, white inputs, and 8px radius. From the first attempt. No corrections. No "actually use our brand blue, not Tailwind's blue-500."

This is the Netcore design system, packaged as an agent skill. I built it so our PMs and designers can generate UI that looks like the product — not like a prototype that needs a design pass before it can be shown to anyone.

It works with Claude, Cursor, Lovable, and any agent that supports the SKILL.md standard. Install it once per workspace and everyone on the team gets it automatically.

**Who this is for:**

- **PMs** — prototype any Netcore screen without explaining the design system every time
- **Designers** — stop correcting AI output before it can go into a review
- **Engineers** — get CSS that actually matches the product when you use AI codegen

---

## What it enforces

When this skill is active, every generation follows these rules — not because the AI is guessing, but because the rules are explicitly loaded into context.

**Manrope. Only Manrope.** Not Inter. Not system-ui. Not whatever font Tailwind defaults to. Manrope, loaded from Google Fonts, on every element.

**White inputs. Always.** `background: #FFFFFF` on every input, select, and textarea. This is the single most common AI generation failure. The page is light. The cards are white. The inputs are white. Dark or grey inputs are wrong — every time.

**Brand blue is `#2F68E5`.** Primary buttons, focus rings, active states, toggle on-states. Not `blue-500`. Not `blue-600`. The exact value.

**8px radius everywhere.** Buttons, inputs, cards, modals, badges — all 8px. The system is consistent. Mixing 6px and 8px across a screen is the kind of thing designers notice immediately, even if they can't name it.

**Toggles are blue, not green.** On-state: `#2F68E5`. Green means success in this system — using it on a toggle is a semantic error that confuses users.

**Three text tiers. No exceptions.** Primary `#17173A` for headings and labels. Secondary `#6F6F8D` for descriptions and helpers. Tertiary `#9494AE` for placeholders and table headers only. Using primary for everything flattens the hierarchy. Using tertiary for labels makes them unreadable.

**No invented values.** If a colour, size, or spacing value isn't in the token table, it doesn't belong in the output. The skill teaches the AI to look up — not make up.

---

## How to use it

Type `/ds` before any prompt to activate the design system:

```
/ds build me a campaign setup form with a name field, audience dropdown, and a scheduling toggle
```

```
/ds create a user management table with status badges and an Invite User modal
```

```
/ds show the analytics dashboard with metric cards and a line chart
```

The `/ds` prefix is the explicit trigger. The skill also activates automatically when Netcore product vocabulary appears in the prompt — campaign, audience, segment, journey, automation, subscriber, analytics, wizard, and more.

Without `/ds`, the AI generates freely. With it, the design system is enforced.

---

## Install

**Cursor** — Settings → Rules → Add Rule → Remote Rule (GitHub) → paste this repo URL.

**Claude Code:**
```bash
mkdir -p ~/.claude/skills/netcore-design-system
curl -o ~/.claude/skills/netcore-design-system/SKILL.md \
  https://raw.githubusercontent.com/YOUR-ORG/netcore-design-system/main/SKILL.md
```

**Lovable / Claude.ai** — Workspace Settings → Skills → Import from URL → paste the raw SKILL.md URL. Enable Workspace skill so the whole team gets it.

---

## Files in this repo

```
SKILL.md                   ← Visual design skill (/ds). This is what you install for UI.
design-system.md           ← Full visual spec — tokens, type scale, all components, decision log
references/
  tokens.md                ← Full CSS token sheet (:root block + Tailwind config)
  components.md            ← Input, button, badge, card, modal, table
  extended.md              ← Stepper, tabs, pagination, accordion, data table, slider
copywriting/                 ← COPYWRITING SKILL FOLDER — install copywriting/SKILL.md for /copy
  SKILL.md                   ← Copy skill entry (/copy · /netcorian · /ux-writing)
  README.md                  ← Folder guide and trigger list
  spec.md                    ← Full Netcorian copy spec (companion to design-system.md)
  references/
    voice.md                 ← Voice, tone, principles
    rules.md                 ← Person, tense, case, punctuation
    patterns.md              ← Surface patterns (buttons, errors, nudges)
    workflows.md             ← Draft + pre-ship checklists
    templates.md             ← Feature, wizard, release note templates
```

### Two skills, one repo

| Skill | Install path | Trigger | Governs |
|---|---|---|---|
| Visual design | `SKILL.md` (repo root) | `/ds` | Colours, fonts, components, layout |
| Copywriting | `copywriting/SKILL.md` | `/copy` | UI strings, voice, tone, microcopy |

---

Built on [Untitled UI v2.0](https://www.figma.com/design/CjXAv82xiIZH2gABXfbHxB). The skill overrides Untitled UI's defaults with Netcore's font, brand colour, and token values. Components not covered here fall back to Untitled UI anatomy.

MIT License.
