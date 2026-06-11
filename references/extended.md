# Netcore — Extended Component Library

Complex components for campaign wizards, dashboards, and data-heavy screens.
Inherit structure from Untitled UI; apply Netcore tokens.

---

## Table of Contents

- [Dropdown Menu](#dropdown-menu)
- [Toggle / Switch](#toggle--switch)
- [Tabs](#tabs)
- [Tooltip](#tooltip)
- [Breadcrumb](#breadcrumb)
- [Pagination](#pagination)
- [Avatar](#avatar)
- [Accordion](#accordion)
- [Stepper / Progress Indicator](#stepper--progress-indicator)
- [Notification / Toast](#notification--toast)
- [Data Table (extended)](#data-table-extended)
- [Slider / Range Input](#slider--range-input)

---

## Dropdown Menu

```css
.dropdown-trigger {
  border-radius: 8px; padding: 9px 36px 9px 12px;
  background: #FFFFFF url("chevron-icon") no-repeat right 12px center;
  border: 1px solid #D9D9E8;
  font-size: 13px; font-weight: 500; cursor: pointer; width: 100%;
}
.dropdown-menu {
  position: absolute; top: calc(100% + 4px); left: 0; right: 0;
  background: #FFFFFF; border: 1px solid #EBEBF5;
  border-radius: 8px; box-shadow: 0 4px 8px rgba(23,23,58,0.12);
  padding: 4px; z-index: 50;
}
.dropdown-item {
  padding: 8px 12px; border-radius: 6px;
  font-size: 13px; font-weight: 500; color: #17173A; cursor: pointer;
}
.dropdown-item:hover    { background: #F6F8FF; }
.dropdown-item.selected { background: #EDF1FF; color: #2F68E5; }
.dropdown-item.disabled { color: #9494AE; cursor: not-allowed; }
```

States: Default · Hover (trigger) · Open · Item hover · Item selected · Disabled

---

## Toggle / Switch

**On state = `#2F68E5` (brand blue) — never green.**

```css
.toggle {
  width: 44px; height: 24px; background: #D9D9E8;
  border-radius: 999px; position: relative;
  cursor: pointer; transition: background 0.15s; border: none;
}
.toggle::after {
  content: ''; position: absolute;
  top: 2px; left: 2px; width: 20px; height: 20px;
  background: #FFFFFF; border-radius: 50%;
  box-shadow: 0 1px 2px rgba(23,23,58,0.08);
  transition: transform 0.15s;
}
.toggle.on           { background: #2F68E5; }
.toggle.on::after    { transform: translateX(20px); }
.toggle:focus        { box-shadow: 0 0 0 4px rgba(47,104,229,0.15); outline: none; }
.toggle.disabled     { opacity: 0.4; cursor: not-allowed; }
```

| Size | Track | Thumb |
|---|---|---|
| sm | 32×18px | 14px |
| md (default) | 44×24px | 20px |
| lg | 56×32px | 28px |

States: Off-Default · Off-Hover · Off-Focused · On-Default · On-Hover · On-Focused · Disabled-Off · Disabled-On

---

## Tabs

```css
/* Underline variant (default) */
.tabs { display: flex; border-bottom: 1px solid #EBEBF5; gap: 0; }
.tab {
  padding: 10px 16px; font-size: 14px; font-weight: 600;
  color: #6F6F8D; cursor: pointer;
  border-bottom: 2px solid transparent; margin-bottom: -1px;
  transition: color 0.1s, border-color 0.1s; white-space: nowrap;
}
.tab:hover    { color: #17173A; }
.tab.active   { color: #2F68E5; border-bottom-color: #2F68E5; }
.tab.disabled { color: #9494AE; cursor: not-allowed; }

/* Pill variant */
.tabs-pill { gap: 4px; border-bottom: none; background: #F5F6FA; border-radius: 8px; padding: 4px; }
.tabs-pill .tab { border-radius: 6px; border-bottom: none; margin-bottom: 0; }
.tabs-pill .tab.active { background: #FFFFFF; color: #17173A; box-shadow: 0 1px 2px rgba(23,23,58,0.08); }
```

States: Default · Hover · Active/Selected · Disabled · (with count badge variant)

---

## Tooltip

```css
.tooltip {
  position: absolute; background: #17173A; color: #FFFFFF;
  font-size: 12px; font-weight: 500; padding: 6px 10px;
  border-radius: 6px; white-space: nowrap;
  pointer-events: none; z-index: 100;
  box-shadow: 0 1px 3px rgba(23,23,58,0.10);
}
.tooltip::after { content: ''; position: absolute; border: 5px solid transparent; }
.tooltip.top::after { top: 100%; left: 50%; transform: translateX(-50%); border-top-color: #17173A; }
.tooltip.bottom::after { bottom: 100%; left: 50%; transform: translateX(-50%); border-bottom-color: #17173A; }
```

Variants: Top · Bottom · Left · Right  
Sizes: sm (label only) · md (title + body)  
Timing: 300ms show delay, 0ms hide delay

---

## Breadcrumb

```css
.breadcrumb { display: flex; align-items: center; gap: 6px; font-size: 13px; font-weight: 500; flex-wrap: wrap; }
.breadcrumb-item     { color: #6F6F8D; }
.breadcrumb-item a   { color: #6F6F8D; text-decoration: none; }
.breadcrumb-item a:hover { color: #2F68E5; }
.breadcrumb-item.current { color: #17173A; font-weight: 600; }
.breadcrumb-sep      { color: #BBBBC8; font-size: 12px; }
```

---

## Pagination

```css
.pagination { display: flex; align-items: center; gap: 4px; }
.page-btn {
  min-width: 36px; height: 36px;
  display: flex; align-items: center; justify-content: center;
  border-radius: 8px; font-size: 13px; font-weight: 600;
  color: #6F6F8D; border: 1px solid transparent; cursor: pointer; transition: background 0.1s;
}
.page-btn:hover    { background: #F5F6FA; color: #17173A; }
.page-btn.active   { background: #EDF1FF; color: #2F68E5; border-color: #2F68E5; }
.page-btn.disabled { color: #9494AE; cursor: not-allowed; }
.page-nav {
  padding: 0 12px; font-size: 13px; font-weight: 600; color: #17173A;
  border: 1px solid #D9D9E8; border-radius: 8px;
  display: flex; align-items: center; height: 36px; gap: 6px;
}
```

---

## Avatar

```css
.avatar {
  border-radius: 50%; object-fit: cover;
  background: #EDF1FF; color: #2F68E5; font-weight: 700;
  display: flex; align-items: center; justify-content: center;
}
.avatar-xs { width: 24px;  height: 24px;  font-size: 10px; }
.avatar-sm { width: 32px;  height: 32px;  font-size: 12px; }
.avatar-md { width: 40px;  height: 40px;  font-size: 14px; }
.avatar-lg { width: 48px;  height: 48px;  font-size: 16px; }
.avatar-xl { width: 64px;  height: 64px;  font-size: 20px; }

/* Status dot */
.avatar-status { width: 10px; height: 10px; border-radius: 50%; border: 2px solid #FFFFFF; position: absolute; bottom: 0; right: 0; }
.status-online  { background: #079455; }
.status-away    { background: #F79009; }
.status-offline { background: #9494AE; }
```

Variants: Image · Initials · Icon placeholder  
Avatar group: overlapping stack (−8px margin), max 5 visible + "+N" overflow badge

---

## Accordion

```css
.accordion { border: 1px solid #EBEBF5; border-radius: 8px; overflow: hidden; }
.accordion + .accordion { margin-top: 8px; }

.accordion-trigger {
  width: 100%; display: flex; align-items: center; justify-content: space-between;
  padding: 16px; font-size: 14px; font-weight: 600; color: #17173A;
  background: #FFFFFF; border: none; cursor: pointer; transition: background 0.1s;
}
.accordion-trigger:hover  { background: #FAFBFF; }
.accordion-trigger.open   { border-bottom: 1px solid #EBEBF5; }
.accordion-chevron        { transition: transform 0.2s; color: #6F6F8D; }
.accordion-trigger.open .accordion-chevron { transform: rotate(180deg); }

.accordion-content { padding: 16px; font-size: 14px; line-height: 22px; color: #6F6F8D; background: #FFFFFF; }
```

States: Closed-Default · Closed-Hover · Open · Disabled  
Variants: Single open (close others on open) · Multiple open

---

## Stepper / Progress Indicator

```css
.stepper { display: flex; align-items: flex-start; gap: 0; }
.step    { flex: 1; display: flex; flex-direction: column; align-items: center; }

.step-circle {
  width: 32px; height: 32px; border-radius: 50%;
  border: 2px solid #D9D9E8; background: #FFFFFF;
  display: flex; align-items: center; justify-content: center;
  font-size: 13px; font-weight: 700; color: #9494AE;
  position: relative; z-index: 1;
}
.step.completed .step-circle { background: #2F68E5; border-color: #2F68E5; color: #FFFFFF; }
.step.active    .step-circle { border-color: #2F68E5; color: #2F68E5; box-shadow: 0 0 0 4px rgba(47,104,229,0.15); }
.step.error     .step-circle { border-color: #C0201A; color: #C0201A; }

.step-label { font-size: 12px; font-weight: 600; color: #9494AE; text-align: center; margin-top: 6px; }
.step.active .step-label    { color: #2F68E5; }
.step.completed .step-label { color: #17173A; }

/* Connector line */
.step-connector { flex: 1; height: 2px; background: #D9D9E8; margin-top: 15px; }
.step-connector.completed { background: #2F68E5; }
```

---

## Notification / Toast

```css
.toast {
  display: flex; align-items: flex-start; gap: 12px;
  background: #FFFFFF; border: 1px solid #EBEBF5; border-radius: 8px;
  padding: 14px 16px; box-shadow: 0 4px 8px rgba(23,23,58,0.12);
  min-width: 320px; max-width: 480px;
}
.toast-icon  { flex-shrink: 0; margin-top: 1px; }
.toast-title { font-size: 14px; font-weight: 700; color: #17173A; }
.toast-body  { font-size: 13px; color: #6F6F8D; margin-top: 2px; }
.toast-close { margin-left: auto; color: #9494AE; cursor: pointer; padding: 2px; }
.toast-close:hover { color: #17173A; }
```

| Type | Left accent stripe | Icon colour |
|---|---|---|
| Info | `3px solid #2F68E5` | Blue |
| Success | `3px solid #079455` | Green |
| Warning | `3px solid #DC6803` | Amber |
| Error | `3px solid #C0201A` | Red |

Positions: Top-right (default) · Top-center · Bottom-right · Bottom-center  
Auto-dismiss: 5s (info/success), stays until dismissed (error/warning)

---

## Data Table (extended)

Building on the base table in components.md:

```css
/* Row selection */
.table tr.selected td { background: #F6F8FF; }

/* Sortable header */
.table th.sortable { cursor: pointer; }
.table th.sortable:hover { color: #17173A; }
.table th.sort-asc::after  { content: ' ↑'; }
.table th.sort-desc::after { content: ' ↓'; }

/* Empty state row */
.table-empty td { text-align: center; padding: 48px 16px; color: #9494AE; font-size: 14px; }

/* Row actions (appear on row hover) */
.table tr:hover .row-actions { opacity: 1; }
.row-actions { opacity: 0; transition: opacity 0.1s; }
```

Variants: Basic · Striped · Bordered · Compact · With row selection · With sorting · With pagination

---

## Slider / Range Input

```css
.slider {
  width: 100%; appearance: none; height: 4px;
  border-radius: 999px; background: #D9D9E8; outline: none;
}
.slider::-webkit-slider-thumb {
  appearance: none; width: 20px; height: 20px;
  border-radius: 50%; background: #2F68E5;
  border: 2px solid #FFFFFF; box-shadow: 0 1px 3px rgba(23,23,58,0.10);
  cursor: pointer;
}
.slider:focus::-webkit-slider-thumb { box-shadow: 0 0 0 4px rgba(47,104,229,0.15); }
.slider:disabled { opacity: 0.4; cursor: not-allowed; }
```
