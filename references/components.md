# Netcore — Core Component CSS

Full CSS for Input, Button, Badge, Card, Side Nav, Modal, Table, Checkbox, Select.
All components inherit anatomy from [Untitled UI v2.0](https://www.figma.com/design/CjXAv82xiIZH2gABXfbHxB) with Netcore token overrides.

---

## Input Field

```css
.input {
  font-family: 'Manrope', sans-serif;
  font-size: 13px; font-weight: 500; line-height: 21px;
  letter-spacing: -0.01em;
  border-radius: 8px;
  padding: 9px 12px;
  width: 100%;
  border: 1px solid #D9D9E8;
  background: #FFFFFF;
  color: #17173A;
  outline: none;
  transition: border-color 0.15s, box-shadow 0.15s;
}
.input-label {
  font-size: 12px; font-weight: 600; line-height: 20px;
  letter-spacing: -0.01em;
  color: #17173A;
  display: block; margin-bottom: 6px;
}
.input-helper {
  font-size: 10px; color: #6F6F8D; margin-top: 5px;
}
.input::placeholder { color: #9494AE; }
```

**All input states:**

| State | Border | Background | Box Shadow | Label | Helper |
|---|---|---|---|---|---|
| Default | `1px #D9D9E8` | `#FFFFFF` | none | `#17173A` | `#6F6F8D` |
| Hover | `1px #9898B0` | `#F6F8FF` | `shadow/xs` | `#17173A` | `#6F6F8D` |
| Focused | `1.5px #2F68E5` | `#FFFFFF` | `ring/brand` | `#2F68E5` | `#6F6F8D` |
| Disabled | `1px #D4D4D4` | `#FAFAFA` | `shadow/disabled` | `#17173A` | `#9494AE` |
| Error | `1.5px #C0201A` | `#FFF5F5` | none | `#17173A` | `#C0201A` |
| Error + focus | `1.5px #C0201A` | `#FFFFFF` | `ring/error` | `#C0201A` | `#C0201A` |
| Warning | `1.5px #DC6803` | `#FFFAEB` | none | `#17173A` | `#B54708` |
| Warning + focus | `1.5px #DC6803` | `#FFFFFF` | `ring/warning` | `#B54708` | `#B54708` |
| Success | `1.5px #079455` | `#F6FEF9` | none | `#17173A` | `#079455` |
| Success + focus | `1.5px #079455` | `#FFFFFF` | `ring/success` | `#079455` | `#079455` |

---

## Button

```css
/* Primary */
.btn-primary {
  background: #2F68E5; color: #FFFFFF; border: none;
  border-radius: 8px; font-size: 14px; font-weight: 600;
  padding: 10px 20px; cursor: pointer; transition: background 0.15s;
}
.btn-primary:hover    { background: #4F7EF0; }
.btn-primary:active   { background: #1F51BE; }
.btn-primary:focus    { box-shadow: 0 0 0 4px rgba(47,104,229,0.15); outline: none; }
.btn-primary:disabled { background: #F5F5F5; color: #9494AE; cursor: not-allowed; pointer-events: none; }

/* Secondary (outlined) */
.btn-secondary {
  background: #FFFFFF; color: #2F68E5;
  border: 1.5px solid #2F68E5; border-radius: 8px;
  font-size: 14px; font-weight: 600; padding: 10px 20px; cursor: pointer;
}
.btn-secondary:hover    { background: #EDF1FF; }
.btn-secondary:active   { background: #D8E6FF; border-color: #1F51BE; color: #1F51BE; }
.btn-secondary:disabled { background: #FAFAFA; border-color: #D4D4D4; color: #9494AE; cursor: not-allowed; pointer-events: none; }

/* Ghost */
.btn-ghost {
  background: transparent; color: #2F68E5; border: none;
  border-radius: 8px; font-size: 14px; font-weight: 600;
  padding: 10px 20px; cursor: pointer;
}
.btn-ghost:hover    { background: #EDF1FF; }
.btn-ghost:active   { background: #D8E6FF; }
.btn-ghost:disabled { color: #9494AE; cursor: not-allowed; pointer-events: none; }

/* Destructive */
.btn-destructive {
  background: #C0201A; color: #FFFFFF; border: none;
  border-radius: 8px; font-size: 14px; font-weight: 600;
  padding: 10px 20px; cursor: pointer;
}
.btn-destructive:hover    { background: #D92D20; }
.btn-destructive:active   { background: #9A1B14; }
.btn-destructive:disabled { background: #F5F5F5; color: #9494AE; cursor: not-allowed; pointer-events: none; }

/* Warning (Untitled UI warning secondary) */
.btn-warning {
  background: #FFFFFF; color: #B54708;
  border: 1.5px solid #DC6803; border-radius: 8px;
  font-size: 14px; font-weight: 600; padding: 10px 20px; cursor: pointer;
}
.btn-warning:hover    { background: #FFFAEB; border-color: #B54708; }
.btn-warning:active   { background: #FEF0C7; border-color: #93370D; color: #93370D; }
.btn-warning:focus    { box-shadow: 0 0 0 4px rgba(220,104,3,0.15); outline: none; }
.btn-warning:disabled { background: #FAFAFA; border-color: #D4D4D4; color: #9494AE; cursor: not-allowed; pointer-events: none; }
```

**Button sizes:**

| Size | Font | Padding | Height |
|---|---|---|---|
| sm | 12px / SB | 6px 14px | 32px |
| md (default) | 14px / SB | 10px 20px | 40px |
| lg | 16px / SB | 12px 24px | 48px |

---

## Badge / Tag

```css
.badge {
  display: inline-block; font-size: 12px; font-weight: 600;
  padding: 5px 14px; border-radius: 8px;
}
.badge-pill { border-radius: 999px; }
```

| Variant | Background | Text |
|---|---|---|
| Brand | `#EDF1FF` | `#1F51BE` |
| Error | `#FFEBE8` | `#9A1B14` |
| Warning | `#FFFAEB` | `#B54708` |
| Success | `#ECFDF3` | `#067647` |
| Neutral | `#EBEBF5` | `#383845` |
| Accent (logo orange) | `#FFF0E8` | `#A63300` |

Sizes: sm `10px / 2px 8px` · md default `12px / 5px 14px` · lg `13px / 6px 16px`

---

## Card

```css
.card {
  background: #FFFFFF; border-radius: 8px;
  border: 1px solid #EBEBF5;
  box-shadow: 0 1px 3px rgba(23,23,58,0.10);
  padding: 24px;
}
.card:hover {
  box-shadow: 0 4px 8px rgba(23,23,58,0.12);
  border-color: #D9D9E8;
}
```

Variants: Default (border + shadow) · Elevated (no border, md shadow) · Outlined (heavier border, no shadow) · Filled (`#FAFBFF` bg)

---

## Side Navigation

```css
.sidenav { background: #291E30; width: 240px; min-height: 100vh; padding: 16px 12px; }
.sidenav-item {
  color: rgba(255,255,255,0.70); font-size: 14px; font-weight: 500;
  padding: 10px 12px; border-radius: 8px; cursor: pointer; transition: background 0.1s;
}
.sidenav-item:hover  { background: rgba(255,255,255,0.08); color: #FFFFFF; }
.sidenav-item.active { background: rgba(47,104,229,0.25); color: #FFFFFF; }
```

---

## Modal / Dialog

```css
.modal-overlay {
  background: rgba(23,23,58,0.5);
  position: fixed; inset: 0;
  display: flex; align-items: center; justify-content: center;
}
.modal {
  background: #FFFFFF; border-radius: 12px;
  box-shadow: 0 8px 24px rgba(23,23,58,0.14);
  padding: 32px; max-width: 520px; width: calc(100% - 32px);
}
.modal-title  { font-size: 18px; font-weight: 700; color: #17173A; margin-bottom: 8px; }
.modal-body   { font-size: 14px; color: #6F6F8D; line-height: 22px; }
.modal-actions { display: flex; gap: 12px; justify-content: flex-end; margin-top: 24px; }
```

---

## Alert / Banner

```css
.alert {
  border-radius: 8px; padding: 14px 16px;
  font-size: 14px; font-weight: 500;
  display: flex; gap: 12px; align-items: flex-start;
}
```

| Variant | Background | Left border | Text |
|---|---|---|---|
| Info | `#EDF1FF` | `3px solid #2F68E5` | `#1F51BE` |
| Warning | `#FFFAEB` | `3px solid #DC6803` | `#B54708` |
| Error | `#FFEBE8` | `3px solid #C0201A` | `#9A1B14` |
| Success | `#ECFDF3` | `3px solid #079455` | `#067647` |

---

## Table (base)

```css
.table { width: 100%; border-collapse: collapse; }
.table th {
  font-size: 12px; font-weight: 600;
  text-transform: uppercase; letter-spacing: 0.07em;
  color: #9494AE; background: #FAFBFF;
  padding: 10px 16px; text-align: left;
  border-bottom: 1px solid #EBEBF5;
}
.table td {
  font-size: 14px; color: #17173A;
  padding: 14px 16px; border-bottom: 1px solid #EBEBF5;
}
.table tr:hover td { background: #F6F8FF; }
.table tr:last-child td { border-bottom: none; }
```

---

## Checkbox & Radio

```css
.checkbox {
  width: 16px; height: 16px; border: 1.5px solid #D9D9E8;
  border-radius: 4px; background: #FFFFFF; cursor: pointer;
  transition: border-color 0.1s, background 0.1s;
}
.checkbox:hover    { border-color: #9898B0; }
.checkbox:checked  { background: #2F68E5; border-color: #2F68E5; }
.checkbox:focus    { box-shadow: 0 0 0 4px rgba(47,104,229,0.15); outline: none; }
.checkbox:disabled { background: #FAFAFA; border-color: #D4D4D4; cursor: not-allowed; }
.radio { border-radius: 50%; } /* same as checkbox otherwise */
```

---

## Select / Dropdown trigger

```css
.select {
  appearance: none;
  background-image: url("chevron-down-icon");
  background-repeat: no-repeat;
  background-position: right 12px center;
  padding-right: 36px; cursor: pointer;
}
/* Inherits all .input states */
```

---

## Universal state helper classes

```css
.is-selected { background: #EDF1FF; border-color: #2F68E5; color: #2F68E5; }
.is-hover    { background: #F6F8FF; border-color: #9898B0; box-shadow: var(--shadow-xs); }
.is-focused  { border: 1.5px solid #2F68E5; box-shadow: var(--ring-brand); outline: none; }
.is-disabled {
  background: #FAFAFA; border-color: #D4D4D4; color: #9494AE;
  box-shadow: 0 1px 2px rgba(0,0,0,0.05);
  pointer-events: none; cursor: not-allowed;
}
```
