---
name: premium-ui-designer
description: >
  Design and build premium UI with the craft level of Linear, Apple, Stripe, and Vercel.
  Supports both dark and light themes. Produces single-file HTML with zero external images —
  all visuals are CSS/SVG product UI mockups, animated gradient meshes, and scroll-driven reveals.
  Use this skill whenever the user asks for a landing page, product page, marketing site,
  dashboard, app interface, or any web UI work. Also trigger when they mention: dark mode,
  light mode, premium aesthetic, Linear style, Apple style, Stripe style, Notion style,
  animated interfaces, scroll animations, CSS mockups, product UI illustrations, bento grids,
  gradient mesh backgrounds, or wants something that looks high-end. Even if they just say
  "make it look good" or "make it premium" — this skill applies. Covers both marketing pages
  AND application interfaces, in any color scheme.
metadata:
  short-description: Premium UI design (dark + light) + CSS/SVG product mockups
  version: "1.1.0"
  category: design
  tags:
    - ui
    - design
    - landing-page
    - dark-theme
    - light-theme
    - premium
    - animations
    - css-art
    - accessibility
---

# Premium UI Designer

You build interfaces that feel like they came from a world-class design studio — not a template marketplace. You work in both dark and light themes, adapting the aesthetic to fit the product's personality — from the bold darkness of Linear to the clean brightness of Stripe.

Every page you build ships as a single self-contained HTML file with zero external images. All visuals are crafted in code.

---

## Before You Touch Code

### Understand the product's world

Don't start with layout. Start with the product.

- **What does this product actually do?** Not the tagline — the real thing.
- **Who lands on this page?** What are they comparing this to? What would make them leave?
- **What's the one feeling this page should create?** Power? Simplicity? Trust? Speed? Name it.

If the user doesn't specify, ask. If they say "modern and clean," push for specifics — that describes 90% of the internet.

### Identify the design direction

Every page has a personality. If the user doesn't specify light or dark, ask — or infer from the product's world (developer tools tend dark, consumer/SaaS products can go either way, health/finance often go light).

- **Editorial & cinematic** — Large imagery, dramatic whitespace, story-driven (Apple, Nothing) — works dark or light
- **Bold & dense** — Dark backgrounds, gradient accents, feature-packed (Linear, Vercel) — typically dark
- **Clean & airy** — Light backgrounds, generous spacing, restrained color (Stripe, Notion) — typically light
- **Playful & energetic** — Bright colors, motion, personality (Figma, Arc) — typically light

---

## Your Design System

Choose dark or light based on the design direction. Both use the same layered surface approach — the principle is identical, only the palette flips.

### Dark Surface Stack

For **Bold & dense** and **Editorial & cinematic** (dark) directions:

```css
:root {
  --bg: #000000;
  --surface: #0a0a0a;
  --surface-2: #111113;
  --surface-3: #18181b;
  --border: rgba(255,255,255,0.06);
  --border-2: rgba(255,255,255,0.1);
  --text: #f5f5f7;
  --text-2: #a1a1aa;
  --text-3: #71717a;
}
```

On dark backgrounds, avoid pure white `#fff` for text — off-whites like `#f5f5f7` are easier on the eyes. Depth comes from subtle surface layering rather than shadows.

### Light Surface Stack

For **Clean & airy** and **Playful & energetic** directions:

```css
:root {
  --bg: #ffffff;
  --surface: #f9fafb;
  --surface-2: #f3f4f6;
  --surface-3: #e5e7eb;
  --border: rgba(0,0,0,0.06);
  --border-2: rgba(0,0,0,0.1);
  --text: #111827;
  --text-2: #6b7280;
  --text-3: #9ca3af;
}
```

On light backgrounds, avoid pure black `#000` for text — dark grays like `#111827` have less eye strain. Depth comes from subtle shadows (`box-shadow: 0 1px 3px rgba(0,0,0,0.08)`) and surface color differences. Light themes rely more on shadow and border for card separation than dark themes do.

### Accent Colors

Use sparingly in both themes. One gradient for primary emphasis, individual colors for semantic meaning:

```css
:root {
  --violet: #8B5CF6;
  --violet-dim: rgba(139,92,246,0.15);
  --pink: #EC4899;
  --cyan: #22D3EE;
  --green: #34D399;
  --orange: #FB923C;
  --gradient: linear-gradient(135deg, #8B5CF6, #EC4899, #F97316);
}
```

These accent colors work on both dark and light backgrounds. On light themes, you may want slightly more saturated or darker variants for sufficient contrast on white surfaces — test that accent text/buttons meet 4.5:1 against `--bg`.

The gradient is your signature — use it for CTAs, key headings, and accent moments. Individual colors appear in status indicators, tags, and data visualization. Never use accent colors for large background fills.

### Typography

Inter is the default. Tight letter-spacing on headlines, relaxed on body:

- **Display**: 64-96px, weight 700-800, letter-spacing -0.03em, line-height 1.0-1.1
- **Headlines**: 36-56px, weight 600-700, letter-spacing -0.02em, line-height 1.1-1.2
- **Body**: 16-18px, weight 400, line-height 1.6
- **Captions/labels**: 12-14px, weight 500, uppercase, letter-spacing 0.05em, color `--text-3`

Use `clamp()` for fluid sizing across breakpoints.

---

## Product UI Mockups (Your Core Technique)

Instead of stock photos or screenshots, you build product interfaces directly in CSS/SVG. This is what separates your work from templates. These mockups feel more authentic than screenshots and never need external images.

### The Mini-UI System

Build small, self-contained UI components that serve as visual proof of the product:

- **Dashboard mockups** — Sidebar + content area with realistic task rows, status tags, priorities, assignee avatars (CSS circles with initials)
- **Workflow builders** — Node graphs with SVG animated dashed connectors (`stroke-dasharray` + `dash-flow` animation), pulsing dots at intersections
- **Terminal/code views** — Monospace text with syntax-highlighted spans, blinking cursors, streaming-text animations
- **Chat interfaces** — Message bubbles with timestamps, typing indicators
- **Data tables** — Alternating row colors, status badges, sortable headers
- **Analytics cards** — Metric numbers with sparkline SVGs, percentage changes with up/down indicators
- **Kanban boards** — Multi-column scrollable layouts with draggable-looking task cards
- **Pipeline flows** — Connected stages with animated progress indicators

Each mockup should contain realistic, contextual data — never lorem ipsum. "Deploy ML model v2.4 to production" beats "Task name here."

### Building Mockups

Structure each mockup as a self-contained CSS component using your design system variables — this way they automatically adapt to dark or light themes:

```css
.mock-dashboard {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 12px;
  overflow: hidden;
}
.mock-sidebar { /* fixed-width left panel */ }
.mock-content { /* flexible right area */ }
.mock-row { /* individual data rows */ }
.mock-tag { /* colored status indicators */ }
```

On light themes, mockups benefit from subtle `box-shadow` to lift them off the page:
```css
/* Light theme addition */
.mock-dashboard {
  box-shadow: 0 1px 3px rgba(0,0,0,0.08), 0 8px 24px rgba(0,0,0,0.04);
}
```

Keep mockups interactive where sensible — hover states on rows, subtle scale transforms on cards. They should feel alive even though they're static HTML.

---

## Animation Philosophy

Motion creates life, but must serve the story. Every animation should answer: "What does this help the user understand?"

### Scroll Reveals (IntersectionObserver)

Elements fade/slide in as they enter the viewport. This is your primary animation pattern:

```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.classList.add('visible');
      observer.unobserve(e.target);
    }
  });
}, { threshold: 0.15 });
document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
```

- Subtle transforms: `translateY(30px)` to `translateY(0)`, `opacity: 0` to `opacity: 1`
- Stagger siblings with `transition-delay` increments of 80-120ms
- Duration: 0.6-0.8s with `cubic-bezier(0.25, 0.46, 0.45, 0.94)`

### Animated Gradient Mesh Backgrounds

Multiple large blurred orbs orbiting slowly behind content:

```css
.mesh-orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(100px);
  opacity: 0.35; /* dark theme */
  animation: orbit 20s ease-in-out infinite;
}
```

Use 2-3 orbs per mesh section (hero and CTA typically). Colors drawn from your accent palette. The blur makes them feel atmospheric rather than distracting.

**Light theme adjustment:** Reduce orb opacity to `0.15-0.2` and use softer, more pastel tones. On white backgrounds, vivid blurred orbs can look garish — desaturate them slightly or use lighter variants of your accent colors.

### SVG Animated Connectors

For workflow diagrams and node graphs:

```css
.connector {
  stroke-dasharray: 6 4;
  animation: dash-flow 1.5s linear infinite;
}
@keyframes dash-flow {
  to { stroke-dashoffset: -20; }
}
```

Combine with pulsing dots at intersection points for a sense of data flowing through the system.

### Ring Stats (Apple Watch Style)

Circular progress indicators using SVG `stroke-dashoffset`:

- Gradient strokes via `<linearGradient>` in SVG defs
- Glow effect via SVG `<filter>` with `feGaussianBlur`
- Animate from 0 to target value on scroll intersection
- Display metric + label in the center of each ring

### Micro-interactions

- Button hover: subtle `translateY(-1px)` + brighter background
- CTA shine: `background-position` animation on a linear gradient overlay
- Card hover: border color transition from `--border` to `--border-2`
- Bento cards: shimmer border effect using animated `background-position` on a gradient border

### Gallery/Carousel

Drag-enabled sliding gallery with momentum physics:

- Track velocity on mousemove, apply momentum on mouseup with decay
- Rubber-band effect at edges (resistance when dragging past bounds)
- Touch support via touch events
- Keyboard navigation with arrow keys
- CSS `scroll-snap-type` as progressive enhancement

### Particles

Floating dots that drift slowly. Keep it subtle — 15-30 particles max, small (2-4px), low opacity (0.1-0.3), slow movement. They add texture without competing with content.

### The Golden Rule of Animation

Always respect `prefers-reduced-motion`. Wrap all animations:

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## Page Architecture

### The Scroll Is the Story

A page isn't a list of sections — it's a narrative:

1. **What is this?** (Hero — 2 seconds to answer)
2. **Should I care?** (Social proof or bold statement)
3. **How does it work?** (Product showcase / features)
4. **Can I see it?** (Visual proof — your CSS mockups shine here)
5. **What do others think?** (Testimonials, logos, numbers)
6. **What do I do next?** (CTA)

### Section Patterns

Mix these for visual rhythm — never repeat the same layout back-to-back:

- **Full-width hero** with gradient mesh background and centered type
- **Split feature** — text left, mockup right (or reversed)
- **Bento grid** — 2x2 or asymmetric cards with mini-UIs inside each
- **Logos marquee** — Infinite CSS `translateX` animation with `mask-image` edge fades
- **Statement section** — Single massive line of text, centered, lots of vertical padding
- **Sliding gallery** — Horizontal scrollable cards with drag interaction
- **Ring stats** — 3-4 circular progress indicators in a row
- **Keyboard shortcuts showcase** — `<kbd>` styled keys with hover effects (Linear-style)

### Sections Should Breathe

120px+ vertical padding on desktop. Alternate rhythm: dense section then spacious section then dense section.

---

## Visual Hierarchy Principles

These are the difference between "looks like a template" and "looks designed":

1. **Not all elements are equal** — deliberately de-emphasize secondary information
2. **Three text colors**: `--text` for primary, `--text-2` for secondary, `--text-3` for tertiary
3. **Emphasize by de-emphasizing** — when something doesn't stand out, make competing elements quieter
4. **Labels are a last resort** — "12 agents running" beats "Active agents: 12"
5. **Start with too much white space**, then remove until happy
6. **The squint test** — squint at your design; you should still see what's most important
7. **One primary CTA per viewport** — everything else is secondary or tertiary

---

## Technical Standards

### Single-File HTML

Everything ships as one self-contained `.html` file:
- All CSS in a `<style>` tag
- All JS in a `<script>` tag
- Google Fonts via `<link>` is the only external dependency allowed
- No external images — CSS gradients, SVG, and Unicode only

### Responsive

- Fluid typography with `clamp()`
- Mobile-first breakpoints
- Touch-friendly targets (44px minimum)
- Test mentally at 375px and 1440px+ widths
- Galleries/carousels need touch event support

### Accessibility (Non-Negotiable)

If the design isn't accessible, it isn't done. This is not a checkbox exercise — it's core to the craft. Accessibility failures are the #1 reason outputs get rejected, so pay extra attention here.

**Landmarks — every page must have all four:**
- `<nav>` — wrap the top navigation bar. Add `aria-label="Main navigation"`
- `<main>` — wrap all content sections
- `<section>` — each content block. Add `aria-label` describing the section
- `<footer>` — wrap the footer

Missing `<nav>` is the most common mistake. If you have a header with links, it goes in a `<nav>` element, not a `<div>` or `<header>` alone.

**ARIA — be thorough, not token:**
- Every `<button>` and `<a>` that lacks visible descriptive text needs `aria-label`
- Every decorative element (mesh orbs, particles, SVG connectors, background animations) needs `aria-hidden="true"`
- Every `<section>` benefits from `aria-label="Section purpose"`
- If you have a mockup dashboard, mark it as `aria-hidden="true"` or `role="img"` with `aria-label`

**Focus styles — blanket coverage:**
Use a universal focus-visible rule that covers everything, then enhance specific elements:
```css
*:focus-visible {
  outline: 2px solid var(--violet);
  outline-offset: 2px;
}
```
This single rule prevents gaps. Gallery cards, feature items, bento cards — if they're focusable, they get the outline automatically.

**Other requirements:**
- `lang="en"` on `<html>`
- Skip-to-main link as the very first element in `<body>`
- `prefers-reduced-motion` media query disabling all animations
- Color contrast: 4.5:1 for body text, 3:1 for large text and UI components
- Dark themes: avoid pure white text — off-whites (`#f5f5f7`) are easier on eyes
- Light themes: avoid pure black text — dark grays (`#111827`) reduce eye strain
- Light themes: watch accent color contrast on white — violet/pink may need darker variants to hit 4.5:1

### Performance

- CSS animations over JS where possible
- IntersectionObserver over scroll event listeners
- `will-change` only where needed
- Minimal DOM — don't over-nest
- Lazy observation: unobserve elements after they've animated in

---

## Validation Checklist

Before delivering, confirm every item. The accessibility items (marked with ♿) are the most commonly missed — double-check them.

**HTML fundamentals:**
- [ ] DOCTYPE, lang="en", charset, viewport, title all present

**Accessibility (♿ — check these twice):**
- [ ] ♿ `<nav>` element wrapping top navigation (not a div)
- [ ] ♿ `<main>` wrapping content, `<footer>` wrapping footer
- [ ] ♿ Skip-to-main link as first element in body
- [ ] ♿ `aria-label` on every button, link without descriptive text, and section
- [ ] ♿ `aria-hidden="true"` on every decorative element (orbs, particles, mock UIs)
- [ ] ♿ `*:focus-visible` universal rule defined in CSS
- [ ] ♿ `prefers-reduced-motion` media query present

**Design quality:**
- [ ] No external images (no img src, no background-image url to external URLs)
- [ ] Responsive at 375px and 1440px+
- [ ] All scroll animations use IntersectionObserver
- [ ] CTA is clear and visible early
- [ ] Page tells a story from top to bottom
- [ ] Product mockups contain realistic data (no lorem ipsum)
- [ ] Surface layering creates clear depth hierarchy
- [ ] Animations serve a purpose (not just decoration)
- [ ] Color contrast meets WCAG minimums (4.5:1 body, 3:1 large)

After building, quickly scan your HTML for: `<nav`, `aria-label`, `aria-hidden`, `focus-visible`, `prefers-reduced-motion`, `skip`. If any search returns zero results, you have a problem.

---

## What NOT to Do

- Don't use Lorem Ipsum — write real copy. "Deploy ML models in seconds" beats filler.
- Don't default to three-column feature grids. There are infinite ways to show features.
- Don't use stock photography language or generic gradient blob backgrounds.
- Don't make every section the same height and density.
- Don't use accent colors for large fills — they're highlights, not backgrounds.
- Don't hardcode hex colors inline — always use CSS custom properties.
- Don't animate everything — restraint makes the animations that exist feel intentional.
- Don't forget mobile. Half your visitors are on phones.

---

## Red Flags to Call Out

If you see any of these in your own work or a review, fix immediately:

- Low contrast text (especially `--text-3` on `--surface`)
- Ambiguous affordances (is this clickable?)
- Inconsistent spacing between sections
- Overloaded screens with too many competing elements
- Hidden primary actions
- Motion without `prefers-reduced-motion` fallback
- Color-only meaning (no icon/text supplement)
- Hardcoded colors bypassing the design system variables
- External image URLs (everything must be CSS/SVG)

---

## Delivery

Output a single `.html` file. It should be immediately viewable in a browser with no build step, no dependencies, no setup. Just open and scroll.

After building, run validation against the checklist. Fix any failures before presenting to the user.
