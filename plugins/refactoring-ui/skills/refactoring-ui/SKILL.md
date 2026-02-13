---
name: ui-design-mastery
description: >
  Expert UI design guidance combining principles from Refactoring UI (Adam Wathan & Steve Schoger),
  Practical UI (Adham Dannaway), Picture This (Molly Bang), and Grid Systems in Graphic Design
  (Josef Müller-Brockmann). Use this skill whenever the user asks for UI/UX design advice, design
  feedback, design reviews, help making interfaces look better, or when creating/reviewing web designs,
  components, layouts, or any visual interface work. Also trigger when users mention: making something
  "look good", improving visual hierarchy, choosing colors, typography, spacing, shadows, layout
  decisions, grid systems, column layouts, or visual composition. Even if the user doesn't explicitly
  say "design" — if they're building UI and want it to look professional, this skill applies. Use it
  alongside code generation when building frontend components.
---

# UI Design Mastery — Complete Design Knowledge

This skill encodes comprehensive design knowledge from four sources: *Refactoring UI*, *Practical UI*, *Picture This*, and *Grid Systems in Graphic Design* (Josef Müller-Brockmann). Apply these principles whenever giving UI design advice, reviewing designs, or generating frontend code. For concrete values (color palettes, spacing systems, type scales, shadow systems, grid construction), see `references/systems.md`. For visual composition principles, see `references/visual-composition.md`.

---

## 1. Starting From Scratch

### Start with a feature, not a layout
Don't begin by designing the shell (nav bars, sidebars, footers). Start with actual functionality — a specific feature the user needs. Design the UI for that feature first. Navigation and layout come later.

### Detail comes later
In early stages, don't obsess over typefaces, shadows, or icons. Work in low fidelity first. Design in grayscale initially to force yourself to use spacing, contrast, and size for hierarchy. Add color later as enhancement.

### Don't design too much
Work in short cycles: design a simple version, build it, iterate, then move to the next feature. Design the smallest useful version first. If something is "nice-to-have", design it later.

### Design for the smallest screen first
Start designing on the smallest screen size. The restricted space forces you to prioritise important elements and remove unnecessary ones. This helps ensure simplicity on larger screens too.

### Choose a personality
Every design communicates a personality through concrete factors:
- **Font choice**: Serif = elegant/classic. Rounded sans-serif = playful. Neutral sans-serif = plain/professional. Light sans-serif = chic/luxurious. Script = handmade or formal.
- **Color**: Blue = safe/familiar. Gold = expensive/sophisticated. Pink = fun/not serious.
- **Border radius**: Small = neutral. Large = playful. None = serious/formal. Stay consistent.
- **Language**: Less personal tone = official/professional. Casual language = friendlier.

### Limit your choices — systematize everything
Don't hand-pick values from a limitless pool. Define constrained systems in advance for: font size, font weight, line height, color, margin, padding, width, height, box shadows, border radius, border width, and opacity. When you have a constrained set, design by process of elimination.

---

## 2. Hierarchy Is Everything

### Not all elements are equal
Visual hierarchy is the most effective tool for making something feel "designed." Deliberately de-emphasize secondary and tertiary information.

### Create hierarchy using multiple properties
Use variations in size, colour, contrast, spacing, position, and depth based on importance:
- **Size** — make important elements larger
- **Colour** — use brighter, richer, warmer, or higher contrast colours for important elements
- **Contrast** — style important elements differently to help them stand out
- **Spacing** — surround important elements with more space
- **Position** — place important elements toward the top or first in a row
- **Depth** — elevate important elements so they appear closer

### Size isn't everything
Don't rely on font size alone. Use font weight and color too:
- **Three text colors**: Dark for primary content, grey for secondary, lighter grey for tertiary.
- **Two font weights**: Normal (400-500) for most text, heavier (600-700) for emphasis.
- Stay away from font weights under 400 for UI work.

### Don't use grey text on colored backgrounds
On colored backgrounds, don't just use grey text or reduce opacity (looks washed out). Hand-pick a color with the same hue as the background, adjusted for saturation and lightness.

### Emphasize by de-emphasizing
When the main element doesn't stand out enough, make competing elements quieter rather than making the main element louder.

### Labels are a last resort
Often you can tell what data is from its format or context. Combine labels and values into single units ("12 left in stock" instead of "In stock: 12"). When you need labels, treat them as secondary.

### Separate visual hierarchy from document hierarchy
Don't let HTML heading tags dictate visual size. Section titles often act as labels — small and supportive, not large and attention-grabbing.

### Test hierarchy with The Squint Test
Squint your eyes and look at your design. You should still be able to tell what's most important. Alternatively: step back, zoom out, or blur the design.

### Semantics are secondary
Design action hierarchy, not semantic equality:
- **Primary actions**: Solid, high-contrast backgrounds. One per screen ideally.
- **Secondary actions**: Outline styles or lower-contrast backgrounds.
- **Tertiary actions**: Styled as links. Discoverable but unobtrusive.
- **Destructive actions**: Secondary/tertiary style normally. Big red button only on the confirmation step.

---

## 3. Layout and Spacing

### Start with too much white space
Give elements way too much space, then remove until happy. In a complete UI, "a little too much" ends up being "just enough." More white space makes designs look simpler, cleaner, and more sophisticated.

### Establish a spacing system
Use a constrained scale based on 8pt increments. Start small for innermost elements, increase as you move outward. See `references/systems.md` for the full scale.

### Space elements based on relatedness
More closely related elements should be closer together. Unrelated elements should have more space between them. Start with extra small spacing for innermost rectangles, gradually increase as you move outward.

### You don't have to fill the whole screen
If you only need 600px, use 600px. Don't spread things out just because you have space.

### Group related elements using four methods
1. **Containers** (borders, shadows, backgrounds) — strongest visual cue
2. **Proximity** — elements near each other appear grouped
3. **Similarity** — similar-looking elements appear grouped
4. **Continuity** — elements aligned in a continuous line appear related

Don't overuse containers — look for opportunities to use spacing, similarity, and continuity to simplify.

### Grids are overrated (but useful)
Use a 12-column grid for main layout alignment. Smaller elements inside containers don't need to align to the grid. Start with 12 columns for desktop, decrease for smaller screens. Gutters should be narrower than columns and remain empty. Sidebars should often have fixed widths.

### Avoid ambiguous spacing
Always have more space around a group than within it. The space between a label and its input should be less than the space between form groups.

### Keep related actions close (Fitts's Law)
The closer and larger a target, the faster it is to select. Ensure targets have at least 48pt × 48pt touch area. Place actions close to the elements they relate to.

---

## 4. Designing Text

### Use a single sans-serif typeface (to start)
Sans serif typefaces are legible, neutral, and simple — suitable for most interfaces. Use a single one until you gain confidence. Then consider a second typeface for headings only.

### Tips for choosing a typeface
- Choose popular, well-tested typefaces (sort by popularity)
- Look for 5+ weights (10+ styles) — indicates higher quality
- Choose taller x-height and greater letter spacing for legibility at small sizes
- When in doubt, use the system font stack
- Steal font choices from well-designed sites

### Use a type scale
Define a set of balanced font sizes rather than arbitrary values. Start with a base size (e.g. 18px), multiply by a scale ratio (e.g. 1.250 Major Third). Round decimals. Use smaller scales for complex apps/dashboards, larger scales for marketing sites. See `references/systems.md`.

### Use only regular and bold weights
Two weights cover almost all needs. Don't use font weights below 400. To de-emphasize text, use lighter color or smaller size, not lighter weight.

### Make long body text at least 18px
Screen sizes have increased; text sizes should too. Most people read from arm's length — ensure body text is legible from that distance.

### Keep line length at 45-75 characters
That's roughly 20-35em. Even with wider surrounding elements, constrain paragraph text. Different widths in the same content area look more polished.

### Line-height is inversely proportional to font size
Small text (12-14px): 1.6-1.75. Body (16-18px): 1.5-1.6. Sub-heads (20-24px): 1.4-1.5. Headlines (30-36px): 1.2-1.3. Display (48px+): 1.0-1.1. For long body text, use at least 1.5. Wider content needs taller line-height.

### Left-align most text
Left alignment is easiest to read — consistent anchor for the eye. Center-alignment works for headlines and short blocks (2-3 lines max). Right-align numbers in tables. Never justify long body text (creates "rivers" of white space, harms readability and accessibility). Try to avoid using multiple alignments within a section.

### Baseline, not center
When mixing font sizes on a single line, align by baseline rather than vertically centering.

### Decrease letter-spacing for large text
Tighten letter-spacing on headlines. Increase letter-spacing on ALL-CAPS text. Leave body text at default.

### Ensure text on photos is legible
Options: semi-transparent gradient overlay, solid overlay, blur background, text shadow, or solid text background.

### Avoid light grey and pure black text
Light grey fails contrast. Pure black (#000) against white causes eye strain. Use accessible dark grey instead.

---

## 5. Working with Color

### Use HSL/HSB instead of hex
Hue (0-360), Saturation (0-100%), Brightness/Lightness. Makes creating palettes intuitive.

### You need more colors than you think
Build complete palettes: 8-10 grey shades, 5-10 shades per primary color, plus accent/semantic colors (red, yellow, green) with full shade ranges.

### Start with 1 brand color
Apply the brand color to interactive elements (links, buttons) to teach users what's interactive. Avoid using brand color on non-interactive elements (could be mistaken for links).

### Create a monochromatic palette
Use variations of the brand color (adjusting saturation and brightness) rather than neutral greys. Creates a cohesive aesthetic. Define 5 key variations with specific purposes:
- **Primary** — actions/interactive elements (must have 4.5:1 contrast against lightest)
- **Darkest** — heading text (very dark grey with tinge of brand color)
- **Dark** — secondary text
- **Medium** — non-decorative borders (3:1 contrast minimum)
- **Light** — decorative borders
- **Lightest** — alternate backgrounds
- **White** — main background

### Define shades up front
Don't use "lighten/darken" functions. Define a fixed palette (see `references/systems.md`):
1. Pick base (shade 500) — works as button background
2. Pick darkest (900, for text) and lightest (100, for tinted backgrounds)
3. Fill gaps: 700, 300 first, then 800, 600, 400, 200

### Don't let lightness kill saturation
Increase saturation for very light and very dark shades. Optionally rotate hue slightly toward bright hues (60/180/300°) for lighter shades.

### Saturate your greys
Add a touch of blue for cool, yellow/orange for warm. Increase saturation on lighter and darker grey shades.

### Avoid pure black
It has too high a contrast against white, causing eye strain. Use a very dark grey instead.

### Use system colors for status
Red = errors/destructive. Amber/Yellow = warnings. Green = success. Always supplement with icons — don't rely on color alone for colorblind users.

### Accessible doesn't have to mean ugly
WCAG: 4.5:1 for normal text, 3:1 for large text and UI components. Consider APCA for better perceptual accuracy, especially on dark backgrounds. When dark-colored backgrounds make hierarchy hard, flip to dark text on light colored background.

### Don't rely on color alone
Always supplement color with icons, patterns, underlines, or contrast differences for colorblind users.

### Adjust photo color temperature to match palette
Cool palettes → cooler photos. Warm palettes → warmer photos. Creates cohesive aesthetic.

---

## 6. Creating Depth

### Emulate a light source from above
Raised elements: lighter top edge, small dark shadow below. Inset elements: darker top edge, lighter bottom edge.

### Use shadows to convey elevation
Define 3-5 fixed shadow levels. Small/tight = slightly raised (buttons). Medium = floating (dropdowns). Large = high elevation (modals). Shadows can have two parts: larger ambient + tighter direct.

### Use color for depth
Light colors look more elevated than dark ones. White cards on grey backgrounds look raised without shadows.

### Even flat designs can have depth
Use lighter/darker elements, solid shadows, and color differences.

### Overlap elements to create layers
Offset elements across boundaries. Give overlapping images an "invisible border" matching the background.

---

## 7. Working with Images

### Use good photos
Bad photos ruin good designs. Use high-quality stock photography or hire a professional.

### Everything has an intended size
Don't scale up icons designed for 16-24px. Enclose small icons in shapes instead. Don't scale down screenshots — use partial views or simplified illustrations.

### Beware user-uploaded content
Use fixed containers with CSS `background-size: cover`. Prevent background bleed with subtle inner shadow, not visible border.

### Use the Rule of Thirds
Divide photos into a 3×3 grid. Align key subjects to the 4 focal points where lines intersect. Creates natural, dynamic composition.

---

## 8. Less Is More

### Remove unnecessary information
Every element competes with existing elements. Remove repeated elements, unneeded words, introductory phrases. Use progressive disclosure.

### Remove unnecessary styles
Avoid decorative colors, backgrounds, and animations that don't convey meaning. Style trends fade — minimal styles age better.

### Don't confuse minimalism with simplicity
Minimal ≠ simple. Removing too much can harm usability. Ensure important actions are visible, labelled, and have sufficient contrast.

### Break up choices (Hick's Law)
Decision time increases with number and complexity of choices. Four strategies: remove choices, group/categorize, break into multiple steps, recommend popular options.

---

## 9. Copywriting for UI

### Be concise
Remove words that don't add information. Avoid filler words ("actually", "basically", "really"). Avoid introductory phrases ("would you like to", "in order to"). Keep sentences under 20 words.

### Use sentence case
Only capitalize first word and proper nouns. Title Case is harder to scan and has inconsistent rules.

### Use plain and simple language
Imagine explaining to a 6th grader. Avoid jargon, slang, and complex words. Use contractions (who's, they're).

### Front-load text
Put key information at the start of headings, lists, and links. "30% off if you sign up today" not "Sign up today for 30% off."

### Use the inverted pyramid
Most important information first, supporting details next, background last.

### Use numerals for numbers
"899" not "eight hundred and ninety nine." Numerals are easier to scan, faster to read, more concise.

### Make links descriptive
"Explore templates" not "Learn more." "Email marketing features" not "Click here."

### Ensure consistent vocabulary
Pick one term and stick with it (e.g. "Sign up" OR "Register", not both).

### Avoid full stops when unnecessary
Most UI text is short enough to not need periods. If you use them, be consistent.

---

## 10. Forms

### Stack forms in a single column
Single column = less interaction cost, less cognitive load, fewer missed fields. Stack labels on top of inputs.

### Minimize form fields
Only ask for essential information. More fields = lower completion rates, more errors.

### Mark both required and optional fields
Required: asterisk * or word "required." Optional: word "optional." Don't assume people will read instructions at the top.

### Match field width to expected input
Width sets expectations. Postcode field should fit 4-5 characters, not span the full width.

### Use conventional field styles
Stick with familiar patterns. Keep iconic elements (radio button circles, checkbox squares) even when customizing.

### Display hints above fields
Not below (gets hidden by autofill menus and keyboards). Tell people constraints before they fill in the field, not after.

### Don't use placeholder text as labels
Placeholder disappears on focus, can look pre-filled, usually fails contrast requirements.

### Use radio buttons over dropdowns (≤10 options)
Radio buttons have lower interaction cost and are always visible. Use autocomplete for long lists.

### Use steppers for small numeric changes
Lower interaction cost than dropdowns. Ensure 48pt minimum button size.

### Validate on submit
Live validation can be distracting. Validate on submit, display error summary at top, errors above each field. Use red + icon (never color alone).

### Write clear error messages
Never blame the user. Be concise. Say what went wrong + how to fix it. Make headings and buttons descriptive.

---

## 11. Buttons

### Define 3 button weights
- **Primary**: Solid fill with brand color, white text. Most prominent. One per screen.
- **Secondary**: Outline/border style with brand color text. Clear but not dominant. Use for equal-importance actions.
- **Tertiary**: Underlined text link style. Discoverable but unobtrusive.

### Button design rules
- 3:1 minimum contrast for button shape against background
- 4.5:1 minimum contrast for button text
- 48pt × 48pt minimum target area
- 16pt minimum space between buttons
- Don't use light grey for secondary buttons (looks disabled)
- Same-function buttons should look the same
- Never rely on color alone to distinguish button types

### Avoid multiple primary buttons
If everything is important, nothing is important. Use secondary or tertiary for repeated actions (like "Follow" buttons in a list).

### Try to avoid disabled buttons
They have low contrast and no feedback. Use alternative patterns instead.

### Left-align buttons
Consistent with left-to-right reading. Place primary action first (leftmost).

### Ensure button text describes the action
"Save article" not "OK." "Update payment details" not "Submit."

### Add friction to destructive actions
Don't make the destructive option the primary button initially. Save the prominent red treatment for the confirmation step.

---

## 12. Grid Systems (Müller-Brockmann)

### The typographic grid
A grid divides a two-dimensional plane into smaller fields or compartments. The fields can be the same size or vary. The column widths are determined by the typeface size. The grid system is a means of ordering and organising content: text, photographs, and illustrations. Uniform content appearance = credibility, professionalism, trust.

### Purpose of the grid
Grids serve three purposes: **economic** (systematic construction = faster production), **rational** (objective, not subjective arrangement of content), and **educational** (conveying complex information clearly and logically). Grid-based design is the visual expression of rational, constructive thinking.

### Column width rules
- Optimal line length: ~7 words per line (roughly 10 words maximum for comfortable reading)
- Column width is directly proportional to type size — larger type demands wider columns
- Too narrow: excessive hyphenation, jagged edges, eye fatigue from constant line breaks
- Too wide: eye loses its place returning to the next line, creates reading fatigue
- For small text (6-8pt): use narrower columns. For body text (9-12pt): moderate columns. For display text (14pt+): wider columns

### Leading (line spacing)
- Leading is inversely proportional to column width — narrow columns need less leading, wide columns need more
- Leading is inversely proportional to type size — smaller type needs proportionally more leading
- Too little leading: lines blur together, eye struggles to track
- Too much leading: lines feel disconnected, text loses cohesion
- Different type sizes on the same page should share a leading grid — ensure all leading is a multiple of a base unit

### Margin proportions
- Margins must never be equal on all sides — this creates dull, static layouts
- Inner margins (gutter) should be narrower than outer margins
- Top margin should differ from bottom margin
- Historical approach: use mathematical ratios (Golden Section, 2:3, 3:4, etc.)
- Well-proportioned margins create a sense of quality and visual sophistication
- The margin area serves functional purposes: space for page numbers, annotations, thumbs

### Page numbers
- Position affects the dynamic quality of the page
- Placing numbers in corners creates different visual rhythms
- Center-bottom is static and calm; outer-bottom is more dynamic
- Page numbers in the margin area keep the type area clean

### Type area construction
- The type area can be divided into 1-10+ columns with various combinations
- More columns = more flexible grid, more layout possibilities
- Fewer columns = simpler, more constrained layout
- The number of columns should match the complexity and variety of content
- A 2-column grid suits simple text. A 3-column grid adds flexibility. 4+ columns handle complex layouts with mixed content (text, images, captions)

### Constructing a grid
- Every design problem is unique and requires its own specific grid
- Start by determining: format (page size), type size, leading, column width, number of columns, margin sizes
- The grid fields are separated by gutters (intermediate spaces) — these must remain empty
- Gutter width should be sufficient to keep columns visually distinct (typically the width of one or two lines of text)
- Vertical divisions create rows; combined with columns they create a matrix of fields
- Images and text blocks should occupy whole grid fields or multiple whole fields — never cut across field boundaries

### Applying the grid
- Grid with 8 fields (2 columns × 4 rows): good for simple layouts, reports, basic publications
- Grid with 20 fields (4 columns × 5 rows): versatile for magazines, catalogs, mixed content
- Grid with 32 fields (8 columns × 4 rows): maximum flexibility for complex publications with varied content sizes
- More grid fields = more design possibilities but requires more discipline
- Photographs, illustrations, and solid tints should align to grid field boundaries
- Consistent grid use across all pages creates unity and visual rhythm throughout a publication

---

## 13. Finishing Touches

### Supercharge the defaults
Replace bullet points with icons. Promote quotes into visual elements. Style links with custom underlines. Use custom checkboxes with brand colors.

### Add color with accent borders
Tops of cards, active nav items, sides of alerts, under headlines, or across the top of the entire layout.

### Decorate backgrounds
Changed background colors per section, subtle gradients (two hues ≤30° apart), repeating patterns, geometric shapes.

### Don't overlook empty states
Include illustration, emphasize the CTA, hide UI that has no purpose yet.

### Use fewer borders
Consider box shadows, different background colors, or more spacing instead.

### Think outside the box
Challenge conventions. Dropdowns can have sections and icons. Tables can combine columns. Radio buttons can become selectable cards.

---

## 14. Accessibility Essentials

### Contrast requirements
- Text ≤18px: 4.5:1 minimum contrast ratio
- Large text (>18px bold or >24px regular): 3:1 minimum
- UI components (form fields, buttons, icons): 3:1 minimum
- Decorative elements: no minimum required

### APCA (next-generation contrast)
More perceptually accurate than WCAG 2, especially for dark interfaces. Key values: 90 (preferred body text), 75 (minimum body), 60 (other text), 45 (large text + UI elements), 30 (placeholder text), 15 (non-text).

### Don't rely on color alone
Supplement with icons, underlines, patterns, borders, or contrast differences. Ensure colorblind users can understand every state.

### Form field borders
Must have 3:1 contrast. Low-contrast form fields are one of the most common accessibility mistakes.

### Assistive technology awareness
Design for screen readers (descriptive labels, logical heading order) and screen magnifiers (limited viewport, close proximity matters).

### Good accessibility = good usability
Accessible interfaces benefit everyone, including those with temporary or situational disabilities.

---

## How to Apply This Skill

When giving design advice or building UI:
1. **Start with hierarchy** — what's most important? Make it dominant.
2. **Use systems** — don't pick arbitrary values. Use defined scales from `references/systems.md`.
3. **Limit choices** — constrained options lead to faster, more consistent decisions.
4. **Add detail progressively** — structure and hierarchy first, then color, depth, and finishing touches.
5. **Minimize usability risks** — have a logical reason for every design detail.
6. **Use common patterns** — follow Jakob's Law; innovate where it counts.
7. **Test with The Squint Test** — squint/blur to verify hierarchy is clear.
8. **When something looks off**, check: hierarchy clear? Enough white space? Spacing relationships unambiguous? Text readable? Contrast sufficient?
