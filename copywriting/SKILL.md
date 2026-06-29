---
name: netcore-copywriting
description: >-
  Netcorian copywriting for Netcore products. Write or review UX writing, microcopy,
  button labels, CTAs, error messages, empty states, tooltips, toasts, modals,
  confirmations, onboarding text, nudges, campaign wizard copy, segmentation labels,
  journey builder copy, release notes, Raman AI messaging, and customer-facing strings.
  Enforces brave/unifying/authoritative voice, jobs-to-be-done framing, user vocabulary
  not jargon, no em dashes. Trigger on /copy, /netcorian, /ux-writing, or when the user
  says write copy, rewrite copy, UX writing, microcopy, button text, error message,
  empty state, tooltip text, toast message, modal copy, CTA label, onboarding copy,
  nudge copy, release notes, in our voice, Netcorian, brand voice, tone of voice,
  wording, label text, helper text, placeholder text, alert message, or review this copy.
---

# Netcore Copywriting (Netcorian)

> **Folder:** `copywriting/` — all copy rules live here. Visual/UI rules live in root `SKILL.md` and `design-system.md`.

Apply these rules to every UI string, alert, empty state, modal, nudge, and customer-facing message.

---

## PRIMARY — Non-negotiables

**Voice:** Brave · Unifying · Authoritative (Netcorian)

**Tone:** Concise · Simple · To the point · Clear · Witty only when safe (never errors or legal)

**Content is king:** Write what the **user** understands, not what engineering or leadership understands.

**Jobs to be done:** Every string must help the user complete a task. If it does not, remove it.

**No em dashes:** Never use `—` in any output. Use a comma, period, colon, or parentheses.

**No jargon:** Use audience, campaign, segment, contacts. Flag internal terms if no plain alternative exists.

**Person & tense:** Address the user as you/your. Never mix me/my and you/your. Present tense for product behaviour.

**Case:** Title Case headings · Sentence case body and helpers · ALL CAPS only for CEE in-product nudge buttons.

**Ship gate:** If usability-tested, utility + usability + usefulness scores must be ≥ 4 before customer release.

---

## Quick reference

```
VOICE     → Brave · Unifying · Authoritative
TONE      → Concise · Simple · Clear · Witty (when safe)
PRINCIPLE → Jobs first · Same terms everywhere · Smart defaults · Design at scale
PUNCT     → No em dashes anywhere
OUTPUT    → Table: Surface | Title | Body | CTA | Notes
```

---

## SECONDARY — When to trigger

### Explicit triggers (user types these)

| Command | Example |
|---|---|
| `/copy` | `/copy write error messages for campaign setup` |
| `/netcorian` | `/netcorian rewrite this CTA in our brand voice` |
| `/ux-writing` | `/ux-writing review these modal strings` |

### Implicit triggers — user phrases

Activate this skill when the request contains any of these intents or words:

**Writing actions:** write copy · rewrite copy · draft copy · improve copy · review copy · edit copy · polish copy · fix copy · wordsmith · wording · phrasing · in our voice · brand voice · tone of voice · Netcorian · Netcore voice

**UX writing:** UX writing · UX copy · microcopy · UI copy · interface copy · product copy · in-app copy

**Surfaces:** button label · button text · CTA · call to action · error message · validation message · empty state · tooltip · toast · banner · alert · modal copy · confirmation · dialog text · onboarding · nudge · helper text · placeholder · field label · form label · status label · release notes · changelog copy

**Netcore product context:** campaign copy · wizard copy · audience copy · segment copy · journey copy · Raman message · co-marketer copy · CEE copy · CDP copy · email copy · push notification copy

### Does NOT trigger (use root `SKILL.md` instead)

- Build, design, prototype, or style UI with no copy to write
- Colour, font, spacing, component, or layout requests
- Generic marketing with no Netcore product context

### Visual design boundary

For tokens, components, spacing → root `SKILL.md` + `design-system.md`. Do not invent colours or fonts in this skill.

---

## Reference files (all inside `copywriting/`)

| File | When to read |
|---|---|
| `references/voice.md` | Voice, tone, design principles → copy |
| `references/rules.md` | Person, tense, case, punctuation, ship gate |
| `references/patterns.md` | Buttons, errors, empty states, modals, nudges, journeys |
| `references/workflows.md` | Draft workflow, pre-ship checklist, user testing gates |
| `references/templates.md` | Feature copy plan, wizard steps, release notes |
| `spec.md` | Full consolidated spec when auditing or onboarding |

---

## Draft workflow

1. Name the user's job
2. Draft headline → body → CTA
3. Voice check: brave, unifying, authoritative?
4. Tone check: concise, simple, clear, witty if appropriate?
5. Hard rules: person, tense, case, no em dashes, no jargon
6. Match terms used elsewhere (segment, audience, campaign)
7. Output as a table; run pre-ship checklist from `references/workflows.md`

---

## Pre-ship checklist (summary)

- [ ] User vocabulary, not internal
- [ ] No em dashes
- [ ] Error, empty, and loading states covered
- [ ] Consistent terms with related flows
- [ ] Novice and veteran would both understand
- [ ] Usability scores ≥ 4 if tested

Full checklist → `references/workflows.md`
