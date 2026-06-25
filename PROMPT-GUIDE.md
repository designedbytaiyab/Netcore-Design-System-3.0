# Prompt Guide — How to get the best output from this skill

This guide is for PMs and team members using the Netcore Design System skill
in Lovable. Follow this format every time for the most accurate results.

---

## The winning format

```
/netcore-design-system [INTENT] the [SCREEN NAME] screen.
Do not [what to avoid]. Use the skill's figma-resources to reference
the exact Figma designs.

The screen must have: [LIST THE 4 PARTS OF THE LAYOUT]

Build these states: [LIST THE STATES IN PLAIN ENGLISH]

Import the nav and panel components from the Figma designs in the skill
— do not generate them from scratch.
Target 60–80% accuracy to the real screen.
```

---

## Why each part matters

| Part | Why it's there |
|---|---|
| `/netcore-design-system` | Activates the skill — without this the AI ignores all the Figma references |
| `[INTENT]` | Use **Replicate** to copy, **Improve** to iterate, **Prototype** to build a flow |
| `Do not redesign` | Without this, the AI invents a new product instead of copying the real one |
| `Use the skill's figma-resources` | Tells the AI to look up the real Figma nodes — not guess the design |
| `The screen must have:` | Anchors the layout — prevents missing panels or wrong structure |
| `Build these states:` | Gives the AI a clear scope — one state per interaction step |
| `Import components from Figma` | Forces nav/panels to come from the real design, not be generated |
| `60–80% accuracy` | Sets a realistic bar — stops the AI over-engineering or quitting |

---

## INTENT — pick the right word

| You want to... | Use this word | Example |
|---|---|---|
| Copy exactly what exists | **Replicate** | "Replicate the campaign setup screen" |
| Add a new feature on top | **Improve** | "Improve the audience filter step" |
| Build a clickable flow | **Prototype** | "Prototype the full campaign creation flow" |
| Start a new screen from scratch | **Build** | "Build a new segment builder screen" |

---

## The 4 parts of every UCE screen

Every UCE screen has the same structure. Always describe all four:

```
1. Left icon nav        — the dark narrow bar on the far left
2. Expanded side panel  — the wider panel showing the section content
                          (e.g. Widgets panel, Saved blocks, Elements)
3. Canvas               — the centre email preview area
4. Right config panel   — the properties panel on the right
                          (General tab + Style tab)
```

---

## Real examples

### Replicate a widget screen
```
/netcore-design-system Replicate the UCE product widget screen exactly
as it exists today. Do not redesign or improve.
Use the skill's figma-resources to reference the exact Figma designs.

The screen must have: the left icon nav, the expanded widgets panel,
the canvas with the product widget block selected, and the right config
panel with dynamic/static product options.

Build these states: empty (no products added), products configured
with dynamic recommendations, products configured with a manual selection.

Import the nav and panel components from the Figma designs in the skill
— do not generate them from scratch.
Target 60–80% accuracy to the real screen.
```

### Improve a specific step
```
/netcore-design-system Improve the UCE dynamic block rule builder.
The current flow has too many steps to set a visibility condition.
Use the skill's figma-resources to reference the existing design first.

The screen must have: the left icon nav, the elements panel, the canvas
with a block selected, and the right config panel showing the dynamic
visibility toggle and rule builder.

Keep the same layout — only improve the rule-building interaction in
the right panel. Do not change the nav or canvas.
Target 60–80% accuracy to the real screen.
```

### Prototype a full flow
```
/netcore-design-system Prototype the full campaign creation flow —
all 10 screens connected and clickable. Use the skill's
figma-resources/campaign-creation folder to reference each screen.

The flow must start at Campaign Home and go through: Type Selection →
Channel Selection → Setup → Audience → Content → Schedule → Preview.

The stepper at the top must update as the user moves through each step.
The summary panel on the right must update in real time.
Use the nav components from the Figma designs — do not generate them.
Target 60–80% accuracy to the real screens.
```

---

## What to avoid

| Do not write this | Write this instead |
|---|---|
| "Redesign the UCE" | "Replicate the UCE [screen name]" |
| "Make it look better" | "Improve the [specific panel] — keep everything else the same" |
| "Build the email builder" | "Replicate the UCE editor with the RSS feed widget selected" |
| "Add a new widget" | "Improve the UCE widgets panel — add [widget name] following the existing widget card style" |
| Vague scope | Name the specific screen, the specific panel, the specific state |

---

## Adding new screens in the future

When new Figma nodes are added to `figma-resources/`, update this guide
with a new example in the Real Examples section above. The prompt format
stays the same — only the screen name, parts, and states change.
