# Design Systems Reference

This reference contains specific, concrete design systems recommended across Refactoring UI, Practical UI, and Grid Systems in Graphic Design (Müller-Brockmann). Use these when building UI components or advising on design decisions.

## Table of Contents
1. [Spacing and Sizing Scale](#spacing-and-sizing-scale)
2. [Type Scale](#type-scale)
3. [Font Weight System](#font-weight-system)
4. [Line Height Guidelines](#line-height-guidelines)
5. [Color Palette Structure](#color-palette-structure)
6. [Shadow Elevation System](#shadow-elevation-system)
7. [Border Radius System](#border-radius-system)
8. [Text Color Hierarchy](#text-color-hierarchy)
9. [Monochromatic Palette Roles](#monochromatic-palette-roles)
10. [Button Hierarchy](#button-hierarchy)
11. [Line Length](#line-length)
12. [Letter Spacing](#letter-spacing)
13. [Z-Index / Elevation Contexts](#z-index--elevation-contexts)
14. [Type Scale Ratios](#type-scale-ratios)
15. [APCA Contrast Values](#apca-contrast-values)
16. [Form Design Checklist](#form-design-checklist)
17. [Grouping Methods](#grouping-methods)

---

## Spacing and Sizing Scale

Base value: 16px. Values increase with progressively larger gaps (no two adjacent values closer than ~25% apart).

```
4px    — Tiny gaps (icon padding, tight inline spacing)
8px    — Small gaps (compact element spacing)
12px   — Medium-small (form input padding, tight margins)
16px   — Base (standard padding, paragraph margins)
24px   — Medium (section padding, card internal spacing)
32px   — Medium-large (between related sections)
48px   — Large (major section spacing)
64px   — Extra-large (page section gaps)
96px   — Hero-level spacing
128px  — Large page sections
192px  — Major layout divisions
256px  — Max container gaps
384px  — Generous layout spacing
512px  — Large containers
640px  — Content widths
768px  — Wider content areas
```

**Usage**: Use this scale for all margin, padding, width, height, and gap values. When choosing a value, start with your best guess, then try the values on either side — one will usually be obviously wrong, making the choice easy.

---

## Type Scale

Hand-crafted scale that provides enough variety without being overwhelming:

```
12px  — Small labels, captions, fine print
14px  — Secondary text, meta information
16px  — Body text (base, browser default)
18px  — Slightly emphasized body text
20px  — Large body / small headings
24px  — Section headings (h3-level)
30px  — Sub-headings (h2-level)
36px  — Page headings (h1-level)
48px  — Display headings
60px  — Hero text
72px  — Large display / marketing headlines
```

**Usage**: Use px or rem units only — never em (nesting causes computed sizes to drift from the scale). This scale aligns well with the spacing system above.

---

## Font Weight System

Two weights cover almost all UI needs:

```
400 or 500  — Normal text (body, descriptions, labels)
600 or 700  — Emphasized text (headings, important labels, active states)
```

**Rules**:
- Never use weights below 400 for UI text — too hard to read at small sizes.
- To de-emphasize text, use lighter color or smaller size, not lighter weight.
- The exact values (400 vs 500, 600 vs 700) depend on the typeface — some fonts look better at 500 normal / 700 bold.

---

## Line Height Guidelines

Line-height is inversely proportional to font size, and proportional to line length:

```
12-14px text  →  line-height: 1.6 - 1.75
16-18px text  →  line-height: 1.5 - 1.6
20-24px text  →  line-height: 1.4 - 1.5
30-36px text  →  line-height: 1.2 - 1.3
48px+ text    →  line-height: 1.0 - 1.1
```

**Adjustments for line length**:
- Narrow content (short lines): can use shorter line-heights in each range
- Wide content (long lines): use taller line-heights — up to 2.0 for very wide body text

---

## Color Palette Structure

### Greys (8-10 shades)
```
50   — Lightest (subtle backgrounds, off-white)
100  — Light backgrounds
200  — Borders, dividers on light backgrounds
300  — Placeholder text, disabled states
400  — Secondary icons
500  — Secondary text
600  — Body text on light backgrounds
700  — Emphasized body text
800  — Headlines, primary text
900  — Darkest (near-black, primary headings)
```

**Note**: Avoid true black (#000). Start with a very dark grey for your 900 shade. Saturate greys slightly — add a touch of blue for cool greys, or yellow/orange for warm greys. Increase saturation on lighter and darker shades to maintain consistent temperature.

### Primary Colors (5-10 shades per color)
```
50   — Ultra-light tint (alert backgrounds, subtle highlights)
100  — Light tint (badges, tag backgrounds)
200  — Light (hover states for light elements)
300  — Medium-light (progress bars, secondary buttons)
400  — Medium (icon colors, link hover)
500  — Base (button backgrounds, active navigation, links)
600  — Dark base (button hover states)
700  — Dark (text on light primary backgrounds)
800  — Very dark (emphasized text with color)
900  — Darkest (headings with color)
```

### Accent / Semantic Colors
Build the same 50-900 shade structure for each:
- **Red** — Destructive actions, errors, negative trends
- **Yellow/Amber** — Warnings, pending states
- **Green** — Success, positive trends, completion
- **Teal/Cyan** — New features, informational highlights
- **Pink/Purple** — Optional accent for categories, promotions

### Building a Shade Scale
1. Pick shade 500 (base) — should work as a button background
2. Pick shade 900 (darkest) — should work as text color
3. Pick shade 50/100 (lightest) — should work as a tinted background
4. Fill 700 and 300 as midpoints
5. Fill remaining gaps: 800, 600, 400, 200
6. Adjust saturation: increase for shades far from 500
7. Optional: rotate hue slightly toward bright hues (60/180/300) for lighter shades, toward dark hues (0/120/240) for darker — keeps colors vivid

---

## Shadow Elevation System

Define 5 fixed shadow levels. Each level uses two shadows: a larger ambient shadow and a tighter direct shadow.

```css
/* Level 1 — Subtle: buttons, cards at rest */
box-shadow:
  0 1px 3px 0 rgba(0, 0, 0, 0.1),
  0 1px 2px -1px rgba(0, 0, 0, 0.1);

/* Level 2 — Low: hoverable cards, popovers */
box-shadow:
  0 4px 6px -1px rgba(0, 0, 0, 0.1),
  0 2px 4px -2px rgba(0, 0, 0, 0.1);

/* Level 3 — Medium: dropdowns, floating panels */
box-shadow:
  0 10px 15px -3px rgba(0, 0, 0, 0.1),
  0 4px 6px -4px rgba(0, 0, 0, 0.1);

/* Level 4 — High: sticky elements, notifications */
box-shadow:
  0 20px 25px -5px rgba(0, 0, 0, 0.1),
  0 8px 10px -6px rgba(0, 0, 0, 0.1);

/* Level 5 — Highest: modals, dialogs */
box-shadow:
  0 25px 50px -12px rgba(0, 0, 0, 0.25);
```

**Usage**:
- Match shadow level to element importance and interaction context
- On click/drag: increase shadow to show element lifting
- On press: decrease shadow (or remove) to show pressing in
- The tight/ambient shadow at lower elevations should fade as elevation increases

---

## Border Radius System

Pick one approach and stay consistent:

```
None (0px)      — Formal, serious, corporate
Small (4-6px)   — Neutral, professional
Medium (8-12px) — Friendly, approachable
Large (16-24px) — Playful, modern
Full (9999px)   — Pills, avatars, badges
```

**Rules**: Don't mix styles. If cards have 8px radius, buttons, inputs, and modals should too (or use a deliberate variation within the system). The full radius (9999px) is appropriate for pill-shaped elements regardless of the base style chosen.

---

## Text Color Hierarchy

On light backgrounds:
```
Primary text    — Dark grey (shade 800-900): headlines, important content
Secondary text  — Medium grey (shade 500-600): dates, descriptions, meta
Tertiary text   — Light grey (shade 400): footnotes, copyright, captions
```

On dark/colored backgrounds:
- Don't use grey text — it looks washed out
- Don't use white text with reduced opacity — it looks disabled
- Hand-pick a color with the same hue as the background, adjusted for saturation and lightness

---

## Button Hierarchy

```
Primary    — Solid background, high contrast, bold. One per screen ideally.
Secondary  — Outline style OR lower-contrast solid background. Clear but not dominant.
Tertiary   — Link-style (no background/border). Discoverable but unobtrusive.
Destructive — Secondary/tertiary style on non-confirmation screens.
             Primary style (red, bold) ONLY on the confirmation step.
```

**Sizing**: Larger buttons should have proportionally more generous padding (not just scaled up). Small buttons should have tighter padding relative to their text size.

---

## Line Length

```
Optimal reading:  45-75 characters per line
CSS equivalent:   20-35em width
Safe maximum:     ~75 characters
```

Even when surrounding content is wider (images, etc.), constrain paragraph text to this range. Different widths in the same content area look more polished than stretching everything to match.

---

## Letter Spacing

```
Headlines (using wide-spaced body font):  Tighten slightly (-0.01 to -0.03em)
All-caps text:                            Increase (+0.05 to +0.1em)
Body text:                                Leave at default (trust the typeface designer)
```

---

## Z-Index / Elevation Contexts

Map shadow levels to typical UI elements:

```
Level 0 (no shadow)  — Flat content, backgrounds, inset elements
Level 1              — Cards, buttons, form inputs
Level 2              — Hovered cards, floating action buttons
Level 3              — Dropdowns, popovers, tooltips
Level 4              — Sticky headers, notifications, toasts
Level 5              — Modals, dialogs, overlays
```

---

## Monochromatic Palette Roles

When building a palette from a single brand color, define these 7 key variations:

```
White     — Main background (#FFFFFF or very close)
Lightest  — Alternate/section backgrounds (very faint tint of brand color)
Light     — Decorative borders, subtle dividers (no contrast minimum)
Medium    — Non-decorative borders (≥3:1 contrast vs white background)
Dark      — Secondary/body text
Darkest   — Headings, primary text (very dark grey with tinge of brand color)
Primary   — Interactive elements: links, buttons, focus rings (≥4.5:1 vs lightest)
```

**Rules**:
- Lightest should be noticeably different from white (use as alternate background)
- Primary must pass 4.5:1 against lightest shade (both are used on interactive elements)
- Darkest should look near-black but carry a subtle tint of the brand hue
- Use the same brand hue across all variations — just shift saturation and lightness

---

## Type Scale Ratios

Common type scale multipliers, ordered from tightest to most dramatic:

```
1.067 — Minor Second     (tight; dense dashboards)
1.125 — Major Second     (compact; data-heavy apps)
1.200 — Minor Third      (balanced; general apps)
1.250 — Major Third      (versatile; most interfaces)
1.333 — Perfect Fourth   (spacious; content sites)
1.414 — Augmented Fourth (bold; editorial layouts)
1.500 — Perfect Fifth    (dramatic; marketing sites)
1.618 — Golden Ratio     (grand; landing pages)
```

**Usage**: Start with base body size (e.g. 18px), multiply repeatedly. Round to nearest whole pixel. Use smaller ratios for complex UIs (dashboards, tools), larger ratios for simple interfaces (marketing, landing pages). Consider switching to a smaller ratio on mobile to prevent text wrapping issues.

---

## APCA Contrast Values

Advanced Perceptual Contrast Algorithm — more accurate than WCAG 2, especially on dark backgrounds:

```
Lc 90   — Preferred body text (fluent reading)
Lc 75   — Minimum body text (still readable)
Lc 60   — Other text (headings, large labels)
Lc 45   — Large text + non-text UI elements
Lc 30   — Placeholder text, disabled states
Lc 15   — Non-text elements (decorative borders, dividers)
```

**Note**: APCA uses "Lc" (Lightness Contrast). Higher = more contrast. Negative values indicate light text on dark background.

---

## Form Design Checklist

Quick-reference checklist for accessible, usable forms:

```
Layout:
  ☐ Single column layout
  ☐ Labels stacked on top of inputs
  ☐ Labels close to their fields (less gap than between field groups)
  ☐ Checkboxes and radio buttons stacked vertically

Fields:
  ☐ Minimal fields — only ask for essential info
  ☐ Field widths match expected input length
  ☐ Both required (*) and optional fields marked
  ☐ Conventional field styles (recognizable patterns)
  ☐ Field borders ≥ 3:1 contrast ratio

Hints & Errors:
  ☐ Hints placed above fields (not below)
  ☐ No placeholder text used as labels
  ☐ Validate on submit (not inline, with exceptions)
  ☐ Error summary at top of form
  ☐ Individual errors above each field
  ☐ Red + icon for errors (never color alone)

Input Types:
  ☐ Radio buttons for ≤10 options (instead of dropdown)
  ☐ Autocomplete for long lists
  ☐ Steppers for small numeric changes
  ☐ Checkbox/toggle for binary options
  ☐ Toggle = immediate effect; Checkbox = needs submit

Long Forms:
  ☐ Break into multiple steps with progress indicator
  ☐ Group related fields under headings
  ☐ Order from easiest to hardest questions
  ☐ Allow review before final confirmation
```

---

## Grouping Methods

Four ways to visually group related elements, from strongest to most subtle:

```
1. Containers     — Borders, shadows, or background colors
                    Strongest cue. Use for critical groupings.
                    Risk: overuse creates visual noise.

2. Proximity      — Place related items closer together
                    Natural, clean approach. No extra visual elements.
                    Rule: space within group < space between groups.

3. Similarity     — Make related items look alike (same color, size, style)
                    Good for repeating patterns (card grids, lists).

4. Continuity     — Align items along a shared line or edge
                    Subtle. Use grid alignment, shared baselines.
```

**Preference order**: Try proximity and similarity first. Use containers only when subtler methods aren't sufficient. Combine methods for stronger grouping.

---

## Grid Construction System (Müller-Brockmann)

### Column Width by Type Size

```
6-8pt type    →  narrow columns (~35-45 characters)
9-10pt type   →  moderate columns (~45-60 characters)
11-12pt type  →  standard columns (~55-75 characters)
14pt+ type    →  wide columns (~60-80+ characters)
```

**Rule**: ~7 words per line is optimal. Maximum ~10 words. Column width must always be proportional to type size.

### Grid Field Configurations

```
2×2 (4 fields)    — Minimal: simple text layouts, basic reports
2×4 (8 fields)    — Simple: straightforward publications, letters
3×3 (9 fields)    — Balanced: brochures, simple magazines
4×4 (16 fields)   — Flexible: magazines, catalogs
4×5 (20 fields)   — Versatile: mixed text and image layouts
5×5 (25 fields)   — Rich: complex editorial, annual reports
8×4 (32 fields)   — Maximum: newspapers, complex multi-content layouts
```

**Usage**: More fields = more layout possibilities but requires more discipline. Content (text blocks, images, tints) should always occupy whole grid fields, never partial fields.

### Leading Grid (Baseline Grid)

All text on a page should align to a common baseline grid. The baseline grid interval is determined by the body text leading:

```
Body text at 10pt/12pt leading  →  baseline grid = 12pt intervals
Body text at 11pt/14pt leading  →  baseline grid = 14pt intervals
Body text at 12pt/16pt leading  →  baseline grid = 16pt intervals
```

**Rule**: All headings, subheadings, captions, and footnotes must have leading that is a whole-number multiple of the baseline grid unit. This ensures all text across columns aligns horizontally.

### Margin Ratios

Classical margin proportions (inner : top : outer : bottom):

```
Simple ratio    →  2 : 3 : 4 : 5
Book standard   →  2 : 3 : 4 : 6
Golden Section  →  inner = 1, outer = inner × 1.618
Symmetrical     →  inner = outer (modern, clean)
```

**Rules**:
- Inner margins (gutter) should always be narrower than outer margins in spreads
- Top margin should be smaller than bottom margin
- Equal margins on all sides = dull, amateur look
- The margin area can hold: page numbers, running heads, annotations, thumb indexes

### Gutter Widths

```
Minimum gutter  →  width of 1 line of body text
Comfortable     →  width of 2 lines of body text
Generous        →  width of 3+ lines of body text
```

**Rule**: Gutters must always remain empty — no text or images should span across them. Gutter width should be consistent throughout the publication.

### DIN Paper Sizes (for reference)

```
A0  →  841 × 1189 mm
A1  →  594 × 841 mm
A2  →  420 × 594 mm
A3  →  297 × 420 mm
A4  →  210 × 297 mm
A5  →  148 × 210 mm
A6  →  105 × 148 mm
```

**Ratio**: All DIN sizes share the ratio 1:√2 (1:1.414). Each size is exactly half the previous size. This means content scales perfectly between sizes.
