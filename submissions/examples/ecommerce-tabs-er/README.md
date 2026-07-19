# E-Commerce Pulse-Active Tabs

Pure CSS tab component with pulse-active animation, designed for e-commerce checkout layouts.

## What it is

A CSS-only tab component using radio buttons for state management. Tab panels pulse in with a smooth scale-bounce transition when switching steps — designed for e-commerce checkout flows. No JavaScript is required.

## How it works

The tab component uses CSS `:checked` pseudo-class on hidden radio buttons to control which panel is visible. The `general sibling combinator` (`~`) selects the corresponding panel.

```css
/* Only show panel matching checked radio */
.tabs__radio:nth-of-type(1):checked ~ .tabs__panels .tabs__panel:nth-child(1) {
    opacity: 1;
    visibility: visible;
    transform: scale(1);
}

/* Pulse-active animation */
.tabs__panel {
    animation: ease-kf-pulse-in 0.4s ease-out forwards;
}
```

Key techniques:
- Hidden `<input type="radio">` controls state — fully keyboard accessible
- `ease-kf-pulse-in` keyframe for smooth pulse entrance (scale overshoot bounce)
- `ease-kf-pulse-glow` for pulsing ring animation on active step number
- `ease-kf-check-pop` for confirmation checkmark pop-in
- Configurable `--ez-pulse-scale` for initial scale factor
- `role="tabpanel"` for screen reader semantics
- CSS custom properties for all colors, timing, and scale

## Why it matters

E-commerce checkout flows need tab components that guide users through steps with clear visual feedback. The pulse-active transition provides a reassuring, responsive feel that keeps users engaged through the purchase funnel — all in pure CSS.

## Files

| File | Purpose |
|------|---------|
| `demo.html` | Full checkout flow with nav, progress steps, and 4 pulse-active tabs (Cart, Shipping, Payment, Confirm) |
| `style.css` | Checkout styles, pulse-active animations, form elements, and responsive rules |

## Custom Properties

| Property | Default | Description |
|----------|---------|-------------|
| `--ez-pulse-duration` | `0.4s` | Pulse animation duration |
| `--ez-pulse-scale` | `1.04` | Initial pulse scale |
| `--ez-pulse-accent` | `#2563eb` | Active tab accent color |
| `--ez-pulse-bg` | `#ffffff` | Background color |
| `--ez-pulse-color` | `#0f172a` | Text color |
| `--ez-pulse-border` | `#e2e8f0` | Border color |

## Keyframes

- `ease-kf-pulse-in` — scale + bounce pulse entrance
- `ease-kf-pulse-glow` — pulsing ring glow on step numbers
- `ease-kf-check-pop` — confirmation checkmark pop-in

## Issue

Closes #50171
