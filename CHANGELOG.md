# Changelog — Netcore Design System 3.0

All notable changes to this skill are documented here.
Format: `[version] — date` · Added / Changed / Fixed

---

## [1.3.0] — 17 Jun 2026

### Added
- `brand-copywriting.md` — full Netcorian copywriting spec (voice, principles, patterns, workflows)
- `copywriting/SKILL.md` — installable copywriting skill with `/copy` and `/netcorian` triggers
- `copywriting/references/` — progressive disclosure: voice, rules, patterns, workflows, templates
- Cross-links from `SKILL.md`, `design-system.md`, and `README.md`

---

## [1.2.0] — 25 Jun 2026

### Changed
- `SKILL.md` — UCE section fully rewritten with real product knowledge sourced from cedocs.netcorecloud.com. Now includes: correct definition of UCE (Unified Content Editor, not User Communication Engine), 3-panel layout spec (left/canvas/right), all block types, Dynamic Blocks, Product Widget, Image Editor, Saved Blocks, Auto-Save, AMP email. Added PM vocabulary map and mandatory clarifying questions AI must ask before generating any UCE design. PATH A (Lovable) and PATH B (Claude Code) flows updated with UCE-specific component areas to scan. Trigger keywords expanded to cover all natural-language ways a PM would reference UCE.

---

## [1.1.0] — 24 Jun 2026

### Added
- `assets/screens/campaign-creation/` — 10 Figma screenshots numbered in flow order (01-home through 10-preview)
- `assets/components/` — top navigation, side nav, text field screenshots
- `flows/campaign-creation/specs.md` — full screen-by-screen interaction map for the campaign creation flow
- `flows/campaign-creation/figma-nodes.md` — Figma node IDs for all 10 screens + DLS components
- `.github/PULL_REQUEST_TEMPLATE.md` — standard PR format for tracking changes
- `CHANGELOG.md` — this file

### Changed
- `SKILL.md` — added Prototype Generation section with trigger map, workflow, and flow table. Skill now handles both design system enforcement and interactive prototype generation.

---

## [1.0.0] — Initial release

### Added
- `SKILL.md` — design system skill with Manrope font, brand blue `#2F68E5`, token rules, and component patterns
- `design-system.md` — full design system documentation
- `references/tokens.md` — color, typography, spacing tokens
- `references/components.md` — component rules
- `references/extended.md` — extended patterns

---

## How to add an entry

When you open a PR, add a new section at the top of this file:

```
## [X.Y.Z] — DD Mon YYYY

### Added
- what was added

### Changed
- what was updated

### Fixed
- what was corrected
```

Version numbering:
- `X` — major (new product area, full redesign)
- `Y` — minor (new flow, new component set)
- `Z` — patch (screenshot update, typo fix, token correction)
