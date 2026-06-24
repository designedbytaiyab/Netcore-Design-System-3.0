# Changelog — Netcore Design System 3.0

All notable changes to this skill are documented here.
Format: `[version] — date` · Added / Changed / Fixed

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
