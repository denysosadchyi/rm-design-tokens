# Records Marine — Design Tokens

CSS дизайн-токени, згенеровані з Figma Variables.

## Файли

- **`primitives.css`** — сирі значення кольорів (105 variables)
  - Blue, Gray Text, Gray Blue, System (Red/Orange/Yellow/Green/Purple/Cyan), Shadow, Specification
- **`tokens.css`** — семантичні токени (132 tokens) — залежить від `primitives.css`
  - Global (bg, text, icon, border), Feedback, Action, Control, Selection, Label

## Використання

```html
<link rel="stylesheet" href="primitives.css">
<link rel="stylesheet" href="tokens.css">
```

```css
.button {
  background: var(--color-action-primary-bg-default);
  color: var(--color-action-primary-text-default);
}
```

## Структура токенів

```
primitives.css:
├── Neutral/         (black, white)
├── Blue/            (25-800)
├── Gray Text/       (50-900)
├── Gray Blue/       (50-900)
├── System/Red/      (base + 50-900)
├── System/Orange/   (base + 50-900)
├── System/Yellow/   (base + 50-900)
├── System/Green/    (base + 50-900)
├── System/Purple    (single)
├── System/Cyan      (single)
├── Shadow/          (sm, lg-low, lg-high, xl)
└── Specification/   (26 категорій постачальників)

tokens.css:
├── Global/
│   ├── bg/          (page, default, subtle, muted, inverse, overlay, brand, brand-subtle)
│   ├── text/        (primary, secondary, tertiary, disabled, inverse, brand, on-brand)
│   ├── icon/        (primary, secondary, disabled, inverse, brand)
│   └── border/      (subtle, default, strong, brand, disabled, focus)
├── Feedback/        (error, warning, success, info) × (bg, bg-solid, bg-subtle, text, border, icon)
├── Action/
│   ├── primary/     (bg/text/icon × default/hover/active/disabled)
│   ├── secondary/   (bg/text/icon × default/hover/active/disabled)
│   ├── ghost/       (bg/border/text/icon × default/hover/active/disabled)
│   ├── neutral/     (bg/border/text/icon × default/hover/disabled)
│   └── danger/      (bg/text/icon/border × default/hover/active/subtle/disabled)
├── Control/
│   ├── field/       (bg/border/text/icon × default/hover/focus/error/disabled/placeholder/active)
│   └── checkbox/    (bg/border × default/checked + icon)
├── Selection/       (bg/text/border/icon × default/hover/active/selected)
└── Label/
    ├── gray/        (bg, bg-solid, border)
    └── blue/        (bg, border)
```

## Source of truth

Figma файл: RM — Library. Два колекції Variables:
- **Primitives** — сирі hex значення
- **Tokens** — aliasи на Primitives (семантичні ролі)
