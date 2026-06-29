---
name: netcore-copywriting
description: Write Netcore product copy in Netcorian voice for UX writing, microcopy, CTAs, error messages, empty states, modals, tooltips, onboarding, campaign wizard labels, and Raman AI messaging. Enforces brave/unifying/authoritative voice, jobs-to-be-done framing, user vocabulary not jargon, no em dashes. Trigger on /copy or /netcorian, and when any request involves writing, rewriting, or reviewing UI strings, button labels, alerts, release notes, or customer-facing copy for Netcore CEE, CDP, PX, Email API, or Raman.
---

# Netcore Copywriting (Netcorian)

Apply these rules to every UI string, alert, empty state, modal, nudge, and customer-facing message. This skill governs **words only**. For colours, fonts, and layout use root `SKILL.md` and `design-system.md`.

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

### Explicit triggers
- `/copy [prompt]` or `/netcorian [prompt]`

### Implicit triggers
Activate when the request involves: UX writing, microcopy, button label, error message, empty state, tooltip, toast, modal copy, onboarding text, nudge copy, release notes, campaign wizard labels, Raman messaging, or "rewrite this in our voice".

### Does not trigger
- Pure UI layout or CSS requests with no copy to write (use root `SKILL.md`)
- Generic marketing with no Netcore product context

### Visual design
For tokens, components, spacing → root `SKILL.md` + `design-system.md`. Do not invent colours or fonts here.

---

## Reference files

| File | When to read |
|---|---|
| `copywriting/references/voice.md` | Voice, tone, design principles → copy |
| `copywriting/references/rules.md` | Person, tense, case, punctuation, ship gate |
| `copywriting/references/patterns.md` | Buttons, errors, empty states, modals, nudges, journeys |
| `copywriting/references/workflows.md` | Draft workflow, pre-ship checklist, user testing gates |
| `copywriting/references/templates.md` | Feature copy plan, wizard steps, release notes |
| `brand-copywriting.md` | Full consolidated spec when auditing or onboarding |

---

## Draft workflow

1. Name the user's job
2. Draft headline → body → CTA
3. Voice check: brave, unifying, authoritative?
4. Tone check: concise, simple, clear, witty if appropriate?
5. Hard rules: person, tense, case, no em dashes, no jargon
6. Match terms used elsewhere (segment, audience, campaign)
7. Output as a table; run pre-ship checklist from `workflows.md`

---

## Pre-ship checklist (summary)

- [ ] User vocabulary, not internal
- [ ] No em dashes
- [ ] Error, empty, and loading states covered
- [ ] Consistent terms with related flows
- [ ] Novice and veteran would both understand
- [ ] Usability scores ≥ 4 if tested

Full checklist → `copywriting/references/workflows.md`
