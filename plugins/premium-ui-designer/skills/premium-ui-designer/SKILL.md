---
name: premium-ui-designer
description: Design and build premium UI with the craft level of Linear, Apple, Stripe, and Vercel. Supports both dark and light themes. Produces single-file HTML with zero external images - all visuals are CSS/SVG product UI mockups, animated gradient meshes, and scroll-driven reveals.
---

This skill guides creation of premium, craft-level UI that matches the quality of Linear, Apple, Stripe, Notion, and Vercel. Every interface should feel intentional, refined, and worthy of these industry-leading standards.

## When to Use

Use this skill when the user asks for:
- Landing pages, product pages, marketing sites
- Dashboards, app interfaces, admin panels
- Dark mode or light mode premium aesthetic
- Linear style, Apple style, Stripe style, Notion style
- Animated interfaces, scroll animations
- CSS mockups, product UI illustrations
- Bento grids, gradient mesh backgrounds
- Anything that should look "high-end" or "premium"

## Design Philosophy

### Visual Hierarchy
- **Generous whitespace**: Let elements breathe. Premium = restraint.
- **Clear focal points**: Guide the eye with intentional contrast.
- **Layered depth**: Subtle shadows, overlays, and z-axis separation.

### Color & Theme
- **Dark themes**: Deep, rich backgrounds (#0a0a0a to #1a1a1a). Subtle gradients. Accent colors that pop.
- **Light themes**: Clean whites with warm or cool undertones. Soft shadows. Refined contrast.
- **Gradient meshes**: Multi-color gradient backgrounds with organic, flowing shapes.
- **Accent colors**: Use sparingly for maximum impact.

### Typography
- **Font choices**: Premium typefaces like SF Pro, Inter (when used well), Söhne, Circular, GT Walsheim.
- **Weight contrast**: Mix weights deliberately - light body, medium labels, bold headlines.
- **Letter spacing**: Slightly loose for uppercase, tight for large headlines.
- **Line height**: Generous (1.5-1.7 for body text).

### Motion & Animation
- **Scroll-driven reveals**: Elements fade/slide in as they enter viewport.
- **Staggered animations**: Sequential timing creates rhythm.
- **Micro-interactions**: Subtle hover states, button feedback.
- **Smooth transitions**: 200-400ms with ease-out curves.
- **CSS-only where possible**: Use CSS animations, @keyframes, and scroll-timeline.

### Layout Patterns
- **Bento grids**: Asymmetric, interesting card layouts (like Apple's feature pages).
- **Full-bleed sections**: Hero areas that command attention.
- **Responsive fluidity**: Designs that adapt gracefully.
- **Asymmetric balance**: Intentional offset, not centered everything.

## Technical Implementation

### Single-File HTML
Output complete, self-contained HTML files:
- All CSS inline or in `<style>` tags
- All JS inline in `<script>` tags
- No external images - use CSS gradients, SVG, or CSS shapes
- All fonts via Google Fonts or system font stacks

### Product UI Mockups
Create interface mockups using pure CSS/SVG:
- Browser chrome with CSS
- App windows with shadows and rounded corners
- Dashboard cards and data visualizations
- Code editors with syntax highlighting

### Gradient Mesh Backgrounds
```css
.gradient-mesh {
  background:
    radial-gradient(at 40% 20%, rgba(99, 102, 241, 0.3) 0px, transparent 50%),
    radial-gradient(at 80% 0%, rgba(168, 85, 247, 0.2) 0px, transparent 50%),
    radial-gradient(at 0% 50%, rgba(59, 130, 246, 0.3) 0px, transparent 50%),
    linear-gradient(to bottom, #0a0a0a, #1a1a1a);
}
```

### Scroll-Driven Reveals
```css
@keyframes fadeInUp {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}

.reveal {
  animation: fadeInUp 0.6s ease-out forwards;
  animation-timeline: view();
  animation-range: entry 0% entry 30%;
}
```

## Quality Checklist

Before delivering any UI:
- [ ] Does it feel premium at first glance?
- [ ] Is the visual hierarchy crystal clear?
- [ ] Are animations smooth and purposeful?
- [ ] Does the color palette feel intentional?
- [ ] Is typography treated with care?
- [ ] Would Linear/Apple/Stripe ship this?

Remember: Premium is not about complexity. It's about every pixel being considered and intentional.
