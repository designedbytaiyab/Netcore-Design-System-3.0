# Netcore Brand Copywriting & Philosophy

> **Source:** [Infinity DS 2.0 on zeroheight](https://netcore.zeroheight.com/759faf070/p/747aa5-introduction) — Overview, Principles, Communication, UX Writing, Usability Testing, Resources.  
> **Purpose:** Single reference for AI agents and humans writing product copy, plans, workflows, and customer-facing content in Netcore's voice.  
> **Design system companion:** Visual/UI rules live in `design-system.md`. This file governs **words, tone, and decision-making**.

---

## 1. Who we are (product context)

Netcore empowers brands to **communicate better with their customers**. The product suite includes:

| Product | Role | Copy angle |
|---|---|---|
| **Netcore CEE** (formerly Smartech) | Omnichannel marketing automation — Email, SMS, Web, App Push, etc. | Data-driven marketers delivering differentiated CX at scale |
| **Netcore Email API** (formerly Pepipost) | High-deliverability transactional email | Speed, reliability, inbox placement |
| **Netcore PX** (formerly Hansel) | No-code in-product experiences — walkthroughs, nudges | Funnel conversion, guided product experiences |
| **UNBXD** | AI-driven eCommerce search, browse, recommendations | Conversion lift through relevance |
| **Netcore CDP** | Unified customer data across channels | Single source of truth, consistent cross-channel experience |
| **Raman** | AI insights and co-marketer capabilities | Sharp, helpful, witty — not robotic |
| **Infinity Design System** | Netcore's design language | Human-centered; seamless human–software interaction |

**One-line brand promise for copy:** Help brands communicate better with customers — through software that is useful, usable, and understandable.

---

## 2. Design principles → copy implications

These six principles from Infinity DS define **how we think**. Every piece of copy should pass through them.

### Jobs to be done

- Write for the **task the user is trying to complete**, not the feature the engineering team built.
- If copy does not help the user achieve their goal, **remove it**.
- Headlines, CTAs, and wizard steps should name the **job** ("Send campaign to cart abandoners") not the system ("Configure broadcast entity").

### Modular design

- Reuse the **same labels and patterns** across products (segmentation, audience, campaign, journey).
- When a flow is shared (e.g. segmentation in Email, Push, SMS), use **identical microcopy** — do not rephrase per channel unless the channel truly differs.

### Consistency

- Show guidance **only when needed** — progressive disclosure in words, not walls of text upfront.
- Do not explain the same thing in a label, helper, tooltip, and modal body.

### Content is king

| Do | Don't |
|---|---|
| Write what **your user** understands | Write what your CxO or engineer understands |
| Use the user's vocabulary ("audience", "campaign", "contacts") | Use internal jargon ("digestification", opaque acronyms) |
| Explain once, clearly | Hide jargon behind an info icon |

### Smart defaults

- Reduce choices in copy: pre-fill, suggest, imply.
- If only one app is integrated, **do not ask** the user to pick an app in the headline or step title.
- Button labels should advance the default happy path ("Next step", "Save and continue") not open-ended ("Proceed").

### Natural behaviour

- Match **familiar mental models** — save/cancel left-right patterns, standard wizard order, conventional error placement.
- Do not invent new verbs for standard actions ("Finalize dispatch" → "Send campaign").

### Design at scale

- Write for **100% of the audience** by default.
- Enterprise-only or single-customer features: **gate in product**, do not clutter global copy for the 99%.
- Never degrade the majority experience to please a vocal minority.

---

## 3. Netcorian voice

**Netcorian** = Netcore's organization-wide writing style. Vision: **austere and comprehensible** — users recognize the brand through UI copy and write-ups.

### Voice (stable — who we are)

Netcore's brand voice is:

| Marker | Meaning in practice |
|---|---|
| **Brave** | Confident recommendations; state what the product does without hedging ("Raman found 3 insights" not "You may possibly have some insights") |
| **Unifying** | Same terms, tone, and patterns across CEE, CDP, PX, Email API, marketing site, and support |
| **Authoritative** | Expert in martech and customer engagement; guide the user like a capable colleague, not a chatbot |

### Tone (flexible — how we sound in context)

From UX Writing Guidelines — tone traits for marketing-tech users (sharp, creative professionals):

| Trait | Rule | Example |
|---|---|---|
| **Concise & precise** | One clear meaning; no vague complexity | Do: "Reach your audience anywhere in the world." Don't: "Reach out to your customers and prospects who has en email address anywhere in any country of the world and boost your online presence to increase sales." |
| **Simple** | Only words needed to communicate the action | Do: "Save changes?" Don't: "Would you like to save your changes?" |
| **To the point** | No filler; no over-engineered personalization in UI | Do: "Get insights from Raman" Don't: "Click here to view insights generated from your campaign data by our AI based brain of Raman" |
| **Clear & understandable** | Readable without tutorials | Do: Plain language anyone can act on Don't: Jargon + tooltip to explain the jargon |
| **Witty, not inappropriate** | Personality in empty states, AI, success — never in errors or legal | Do: "Raman just dived deep into your data and came up with 3 new insights" Don't: Long passive constructions about what happened while you were away |

---

## 4. Hard rules (non-negotiable)

### Audience & expertise

- Write for **people of all expertise levels** — beginners and industry veterans.
- Avoid terms that sound "too techie" unless the audience is explicitly technical (API docs).
- UI copy should be understandable **without** tutorial videos, guides, or smoke screens.

### Person & tense

- **First person for the product** when addressing the user: "your campaign", "your audience".
- **Never mix** "me/my" and "you/your" in the same phrase.
- **Present tense** for product behaviour ("Saves automatically"). Use past/future only when describing a specific event.

### Labels & UI elements

- Refer to controls **by their visible label**, not by type ("Click **Save**" not "Click the primary button").
- Use **consistent words** for the same concept everywhere (don't alternate "contacts", "users", "subscribers" in one flow without reason).

### Punctuation

- **No em dashes (—) anywhere.** Do not use `—` in UI copy, marketing, release notes, emails, or docs. Use a comma, period, colon, or parentheses instead.
  - Don't: "Your campaign is ready — send it now"
  - Do: "Your campaign is ready. Send it now." or "Your campaign is ready: send it now"
- Hyphens (`-`) are fine for compound modifiers and product names where standard English requires them.

### Case system

| Case | Use for |
|---|---|
| **Title Case** | Main headings, short introductions |
| **Sentence case** | Paragraphs, descriptions, helper text, body copy |
| **ALL CAPS** | Button labels in **in-product nudges** (CEE nudge spec); use sparingly elsewhere |

### Transparency

- When something takes time, **say why** — spinners without context erode trust.
- Error and empty states must clarify **what happened** and **what to do next**.

### Usefulness bar (from usability testing)

Before shipping feature copy to customers:

- **Utility + Usability + Usefulness** scores should be **≥ 4** (qualitative testing benchmark).
- If score ≤ 4: hold release and improve copy/UX — do not ship and patch later.

---

## 5. Copy patterns by surface

### Buttons & CTAs

- Verb-first, outcome-clear: "Create campaign", "Save", "Next step", "Send test email".
- Questions only when confirming destructive or irreversible actions: "Delete this segment?"
- Wizard primary action: always advance the job ("Next step"), secondary: "Save".

### Headings & structure

- **Answer-first:** lead with what the user can do or learn, then supporting detail.
- Section title = job or object ("Audience", "Schedule", "Content").
- Subtitle = one line of context in secondary voice — never repeat the title.

### Errors & alerts

- State **what went wrong** + **how to fix** in plain language.
- No wit, blame, or jargon.
- Use "must" / "required" only on errors and critical alerts — not on neutral actions.

### Empty states

- Explain **why it's empty** and **one clear next action**.
- Wit allowed if it does not obscure the action.

### 404 & not-found

- Clarify: the system is working; the **requested data** is unavailable.
- Offer navigation back to a known safe place.

### Modals & confirmations

- Title = decision or outcome ("Discard unsaved changes?").
- Body = consequence in one or two sentences.
- Actions: label the outcome ("Discard", "Keep editing") not "Yes"/"No".

### Toasts & flags

- Title: what happened (sentence case, bold).
- Body: detail or next step (secondary tone).
- Auto-dismiss info/success; keep errors/warnings until dismissed.

### In-product nudges (CEE)

| Nudge type | Background | Text | Buttons |
|---|---|---|---|
| No CTA | `#191919` | `#FFFFFF` | Close icon white; backdrop `#17173A` @ 50% opacity |
| With CTA | `#FFFFFF` | Title `#17173A`, body `#6F6F8D` | Primary: `#143F93` fill, white ALL CAPS text; Secondary only when required |
| Spotlight | Overlay 0.7–0.8 | Bold body if legibility suffers | White button, ALL CAPS |

> **Note:** Design System 3.0 uses `#2F68E5` for primary UI actions; nudge spec on zeroheight still references `#143F93` (2.0). For new work, align nudge primary buttons with current brand blue unless product explicitly maintains 2.0 nudge tokens.

### Segmentation & journey copy

- **Segmentation:** emphasize personalized, relevant messaging — "customers who added 2 products to cart in the last week".
- **Journey:** map orchestration in user language — triggers, conditions, actions, flow controls; avoid builder-internal node names in user-facing labels.

---

## 6. Workflows

### Workflow A — Draft any UI copy

```
1. Name the user's job (Jobs to be done)
2. Draft headline → body → CTA in that order
3. Run voice check: brave, unifying, authoritative?
4. Run tone check: concise, simple, to the point, clear, appropriately witty?
5. Run hard rules: person, tense, case, labels, jargon, no em dashes
6. Compare to modular terms used elsewhere in the product
7. Cut anything that does not help the user complete the job
```

### Workflow B — Copy review before ship

```
- [ ] User vocabulary, not internal vocabulary
- [ ] No jargon without plain-language alternative
- [ ] Consistent terms with related flows (segmentation, campaign, audience)
- [ ] Smart default reflected (no unnecessary choices in copy)
- [ ] Error/empty/loading states included
- [ ] Case rules applied (Title / Sentence / ALL CAPS)
- [ ] No em dashes (—) anywhere in the copy
- [ ] First person consistent; present tense for behaviour
- [ ] Controls referenced by label text
- [ ] Would a novice and a veteran both understand this?
- [ ] Usability scores ≥ 4 (if feature was tested)
```

### Workflow C — Qualitative copy validation

Test only what you are **willing to change**. Prioritize:

- Implementations with significant compromises
- Key differentiators
- Critical user problems
- Areas where the team was uncomfortable

**Ask:**

| Dimension | Example questions |
|---|---|
| Utility | Do you need this? Does it solve your problem? How often will you use it? |
| Usability | Could you complete the task? How long? How many mistakes? Could you repeat without help? |
| Trust & aesthetics | Rate ease 1–5, trust 1–5 |

**Release gate:** combined usefulness bar ≥ 4.

### Workflow D — Quantitative copy validation

When choosing between two phrasings:

- **A/B test** microcopy on real flows
- **5-second / first-glance test** — is the primary action obvious?
- **First-click test** — where do users go first?

Let data break ties; default to simpler copy when results are equal.

### Workflow E — Cross-channel content (marketing, email, in-app)

```
1. Same Netcorian voice markers
2. Same product names and capitalization (Netcore CEE, Raman, CDP)
3. Adapt length to channel — UI shortest, email can breathe, docs deepest
4. Never contradict in-app terminology in outbound comms
```

---

## 7. Plan & document templates

Use these structures so AI and humans produce consistent output.

### Feature copy plan

```markdown
## Feature: [name]
**User job:** [what they're trying to accomplish]
**Audience slice:** [all users | segment | enterprise-only]
**Primary action:** [one verb]

### Strings
| Surface | Title | Body | CTA |
|---|---|---|---|
| Entry | | | |
| Empty | | | |
| Loading | | | |
| Success | | | |
| Error | | | |

### Terms locked
- [e.g. audience, segment, campaign]

### Out of scope for v1 copy
- [features we are not exposing to 99% of users]
```

### Campaign / wizard step copy

```markdown
## Step: [Setup | Content | Audience | Schedule]
**Job this step completes:**
**Fields:** label (required?) + helper (one line max)
**Primary CTA:** Next step / Send
**Secondary:** Save
**Summary sidebar labels:** match form labels exactly
```

### Release notes (product voice)

```markdown
## [version] — [month year]
**Theme:** [one line]

### New
- [User benefit, not engineering milestone]

### Improved
- [What got faster, clearer, or simpler]

### Fixed
- [What the user would have noticed]
```

---

## 8. AI usage instructions

When an AI agent writes Netcore copy, it must:

1. **Read this file first** for voice, principles, and gates.
2. **Read `design-system.md`** only for UI string length/layout constraints — not for voice.
3. **Default to Netcorian:** brave, unifying, authoritative + concise, simple, clear.
4. **Never invent product names** — use the table in §1.
5. **Output copy in tables** (surface × title × body × CTA) for reviewability.
6. **Flag jargon** explicitly if no plain alternative exists.
7. **Never use em dashes (—)** in any output copy.
8. **Run Workflow B checklist** mentally before returning final copy.

### Prompt stub for teams

```
Write [surface] copy for Netcore [product].
User job: [job]
Follow netcore-brand-copywriting.md — Netcorian voice, design principles, case rules.
Return a table: Surface | Title | Body | CTA | Notes
```

---

## 9. Where else to use this philosophy

| Area | How to apply |
|---|---|
| **Cursor / Claude skills** | Convert §2–§8 into `SKILL.md` with YAML description triggers: "UX writing", "microcopy", "button labels", "error messages", "Netcorian" |
| **Design system docs** | Link from zeroheight Communication section; keep visual and verbal systems paired |
| **Figma / component specs** | Every component page: default label, helper, error, empty strings in Netcorian voice |
| **PRD & spec templates** | "User job" and "copy plan" sections mandatory before dev |
| **QA / UAT scripts** | Validate visible strings against locked terms and case rules |
| **Support & help centre** | Same vocabulary as product UI — no parallel glossary |
| **Marketing site & ads** | Brand promise + authoritative martech tone; avoid hype that product UI cannot deliver |
| **Sales decks & demos** | Jobs-to-be-done framing; show modular flows (segment once, use everywhere) |
| **Email templates & lifecycle comms** | Sentence case body; clear single CTA; product name consistency |
| **AI features (Raman, co-pilot)** | Witty-but-clear voice; first-person product; transparent about what AI did |
| **Onboarding & nudges (PX, CEE)** | Short, ALL CAPS nudge buttons per spec; transparent loading copy |
| **API & developer docs** | Authoritative and precise; may use technical terms when audience is developers |
| **Hiring & internal comms** | "Design at scale" and "content is king" as shared product culture language |
| **Usability testing** | Score utility/usability/usefulness before release; copy is part of the test artifact |
| **Localization briefs** | Netcorian rules travel with glossary — do not translate internal jargon that should be rewritten |

---

## 10. Quick reference card

```
VOICE     → Brave · Unifying · Authoritative (Netcorian)
TONE      → Concise · Simple · To the point · Clear · Witty (when safe)
PRINCIPLE → Jobs · Modular · Consistent · Content is king · Smart defaults · Natural · At scale
PERSON    → You/your (user); never mix me/my + you/your
TENSE     → Present for product behaviour
CASE      → Title headings · Sentence body · ALL CAPS nudge buttons only
PUNCT     → No em dashes (—) anywhere — use comma, period, or colon instead
JARGON    → User words, not engineer/CxO words
SHIP GATE → Usefulness scores ≥ 4 when tested
```

---

## 11. Gaps & follow-ups

Content on zeroheight **UX Writing** sub-pages (*Writing Essentials*, *Checklist*, *Inspiration* tabs) did not fully load in automated extraction. The **(OLD) UX Writing Guidelines** page was used as the detailed source for tone traits and rules. Recommend:

1. Export or paste those tab contents into this repo to complete the checklist and voice markers.
2. Reconcile nudge button colour (`#143F93` vs DS 3.0 `#2F68E5`) in one authoritative note.
3. Promote this file to a formal Cursor skill when ready (`netcore-copywriting/SKILL.md`).

---

*Last synthesized from Infinity DS 2.0 zeroheight, June 2026.*
