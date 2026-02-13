---
name: refactoring-ui
description: Expert UI design guidance combining principles from Refactoring UI (Adam Wathan & Steve Schoger), Practical UI (Adham Dannaway), Picture This (Molly Bang), and Grid Systems in Graphic Design (Josef Muller-Brockmann). Use this skill whenever the user asks for UI/UX design advice, design feedback, design reviews, help making interfaces look better, or when creating/reviewing web designs, components, layouts, or any visual interface work.
---

This skill provides expert UI design guidance based on established design principles from industry-leading resources. Use these principles to create or critique interfaces.

## When to Use

Trigger this skill when users:
- Ask for UI/UX design advice
- Request design feedback or reviews
- Want to make interfaces "look better"
- Are creating or reviewing web designs
- Need help with visual hierarchy, colors, typography, spacing
- Ask about layout decisions, grid systems, column layouts
- Want help with visual composition
- Are building frontend components and want them to look professional

## Core Principles

### 1. Hierarchy is Everything
**From Refactoring UI**

Not all elements are equally important. Use visual weight to guide the eye:

- **Size**: Important elements should be larger.
- **Weight**: Bold text draws attention; light text recedes.
- **Color**: High contrast for primary; muted for secondary.
- **Spacing**: More space around important elements.

**Anti-pattern**: Making everything look the same importance. If everything is bold, nothing is bold.

### 2. Start with Too Much White Space
**From Refactoring UI**

White space is not wasted space - it's a design element:

- Add more padding than you think you need.
- Increase line-height for readability.
- Give sections room to breathe.
- Then selectively reduce if needed.

**Practical spacing scale**: 4, 8, 12, 16, 24, 32, 48, 64, 96, 128px

### 3. Work in HSL, Not Hex
**From Refactoring UI**

HSL (Hue, Saturation, Lightness) is more intuitive:

- **Hue**: The color (0-360 degrees)
- **Saturation**: Intensity (0-100%)
- **Lightness**: How light/dark (0-100%)

Building a color palette:
1. Pick a base color.
2. Create 9 shades by adjusting lightness.
3. Shift hue slightly for warmer/cooler shadows.

### 4. Establish Clear Systems
**From Practical UI**

Don't make decisions in isolation:

- **Type scale**: e.g., 12, 14, 16, 18, 20, 24, 30, 36, 48, 60px
- **Spacing scale**: 4, 8, 16, 24, 32, 48, 64px
- **Border radius**: Pick 2-3 values and stick to them.
- **Shadow scale**: Consistent elevation levels.

### 5. Use Visual Weight Consciously
**From Picture This**

Every element has visual weight based on:

- **Size**: Larger = heavier
- **Color**: Darker = heavier, brighter = heavier
- **Position**: Lower on page = heavier
- **Isolation**: Isolated elements feel heavier
- **Complexity**: Detailed elements feel heavier

Balance the composition - not necessarily symmetrically.

### 6. Grid Systems Create Order
**From Grid Systems in Graphic Design**

Use grids for consistent, harmonious layouts:

- **12-column grid**: Maximum flexibility.
- **8-point grid**: Align everything to 8px increments.
- **Baseline grid**: Align text vertically.
- **Gutter consistency**: Same spacing between columns.

Breaking the grid intentionally creates emphasis.

## Specific Guidance

### Typography

**Font Pairing**
- Pair a display font with a body font.
- Contrast in style (serif + sans-serif) or weight.
- Max 2-3 fonts per project.

**Font Sizing**
- Body: 16-18px minimum for readability.
- Headlines: 1.5-3x body size.
- Scale: Use a modular scale (1.25, 1.333, 1.5 ratio).

**Line Height**
- Body text: 1.5-1.7
- Headlines: 1.1-1.3
- Shorter lines need less line-height.

### Color

**Building Palettes**
1. Choose 1-2 primary colors.
2. Add 1 accent color.
3. Create 8-10 neutral grays.
4. Generate light/dark variants of each.

**Using Color**
- Grays for most text and backgrounds.
- Primary for main actions and key elements.
- Accent sparingly for emphasis.
- Semantic colors: red (error), green (success), yellow (warning).

**Dark Mode**
- Don't just invert colors.
- Reduce contrast slightly (not pure white text).
- Desaturate bright colors.
- Add depth with subtle elevation.

### Layout & Spacing

**Component Spacing**
- Related items: 8-16px apart.
- Groups of items: 24-32px apart.
- Sections: 48-96px apart.

**Padding Rules**
- Buttons: 12-16px vertical, 24-32px horizontal.
- Cards: 16-24px padding.
- Containers: 16-64px depending on viewport.

**Alignment**
- Left-align body text.
- Center sparingly (short headlines, CTAs).
- Maintain consistent left edges.

### Visual Polish

**Shadows**
- Subtle shadows create depth.
- Multiple shadow layers look more realistic.
- Shadow direction should be consistent.

```css
/* Layered shadow */
box-shadow:
  0 1px 2px rgba(0,0,0,0.05),
  0 4px 8px rgba(0,0,0,0.1),
  0 16px 32px rgba(0,0,0,0.1);
```

**Borders**
- Use sparingly - spacing often works better.
- Light borders (1px, low opacity).
- Or use background color differences instead.

**Gradients**
- Subtle gradients add depth.
- Direction: top-to-bottom or top-left-to-bottom-right.
- Low contrast between colors.

## Design Review Checklist

When reviewing UI, check:

- [ ] Is the visual hierarchy clear?
- [ ] Is there enough white space?
- [ ] Are colors consistent and intentional?
- [ ] Is typography readable and well-scaled?
- [ ] Does spacing follow a system?
- [ ] Is alignment consistent?
- [ ] Are interactive elements obvious?
- [ ] Does it look polished (shadows, borders, details)?
- [ ] Is it accessible (contrast, touch targets)?

## Common Fixes

| Problem | Solution |
|---------|----------|
| Looks cluttered | Add more white space |
| Feels flat | Add subtle shadows and depth |
| Text hard to read | Increase contrast, adjust line-height |
| Looks unpolished | Consistent spacing, align elements |
| Colors clash | Use HSL to create harmonious palette |
| Layout feels random | Apply a grid system |
| Too many focal points | Establish clear hierarchy |
