# Zoom-In Feature Grid — SaaS Showcase

A pure CSS feature grid component for SaaS product pages. Each card scales up and reveals a radial glow on hover, while the icon zooms in for emphasis.

## How It Works

Cards use CSS transitions on `transform`, `background`, `box-shadow`, and `border-color`. A `::before` pseudo-element creates the top-down radial glow. The icon uses a separate `scale()` transform on hover.

## Running the Demo

Open `demo.html` in any modern browser. Keep `style.css` in the same folder. No build step required.

## Customization

All colours, spacing, and timing are controlled through CSS custom properties defined on `:root`:

```css
:root {
  --zoom-bg: #080e1e;
  --zoom-card-bg: #111b2e;
  --zoom-card-active: #182240;
  --zoom-label: #cbd5e1;
  --zoom-heading: #f8fafc;
  --zoom-body-text: #8b9ab5;
  --zoom-accent: #34d399;
  --zoom-glow: rgba(52, 211, 153, 0.14);
  --zoom-stroke: rgba(255, 255, 255, 0.06);
  --zoom-ratio: 18px;
  --zoom-spread: 1.5rem;
  --zoom-dur: 0.38s;
  --zoom-ease: cubic-bezier(0.22, 1, 0.36, 1);
}
```

Override any variable to match your brand palette.

## Responsive Breakpoints

- Desktop: 3-column grid
- Tablet (below 920px): 2 columns
- Mobile (below 580px): single column stack

## Accessibility

- `prefers-reduced-motion` disables all transitions and transforms
- Cards are focusable via `tabindex="0"` and respond to `:focus-within`
- `focus-visible` outline on links
- Semantic HTML with `article`, `h2`, `role="list"`, and `aria-hidden` on decorative elements

## Tech

HTML + CSS only. No JavaScript. No external dependencies.
