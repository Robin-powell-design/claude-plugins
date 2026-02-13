---
name: social-media
description: Create social media visuals as single-file HTML — posts, stories, carousels, banners, and cards for Instagram, LinkedIn, X/Twitter, and other platforms. Use this skill whenever the user asks for a social media post, social graphic, story, carousel, banner, cover image, Open Graph image, promotional visual, quote card, announcement graphic, or any visual content meant for social platforms. Also trigger for "make me a post about...", "create a visual for...", "design a graphic for...", or "social content for...". NOT for landing pages or app interfaces.
---

# Social Media Visual Designer

Create scroll-stopping social media visuals as self-contained HTML files that can be screenshotted or exported.

## Why HTML?

Social media visuals built in HTML/CSS give you full creative control — custom typography, animated elements, precise layouts, gradient effects, and SVG illustrations — all without needing Figma, Canva, or Photoshop. The output is a pixel-perfect HTML file sized to the exact platform dimensions. The user screenshots or exports it to get their final image.

---

## Before Designing

### Ask (or infer) these:

- **Platform & format** — Instagram post? LinkedIn banner? X card? Story? Carousel? Each has specific dimensions.
- **What's the message?** — What's the one thing someone should take away in 1.5 seconds of scrolling?
- **Brand context** — Colors, fonts, tone? If unknown, ask or suggest a direction.
- **Content type** — Announcement? Quote? Data/stat? Tutorial? Promotional? Behind-the-scenes?

If the user gives you a topic and no other context, make a creative decision and go. Don't over-ask — ship something bold and iterate.

---

## Platform Dimensions

Always set the HTML `<body>` and container to the exact pixel dimensions for the target platform. The page background should fill the entire canvas with no scrolling.

### Instagram
- **Post (square):** 1080 × 1080px
- **Post (portrait):** 1080 × 1350px (recommended — takes up more feed space)
- **Story / Reel cover:** 1080 × 1920px
- **Carousel slide:** 1080 × 1080px or 1080 × 1350px (each slide is a separate HTML file)

### LinkedIn
- **Post image:** 1200 × 627px
- **Article cover:** 1200 × 644px
- **Banner / cover:** 1584 × 396px
- **Carousel slide:** 1080 × 1080px or 1080 × 1350px (PDF export, but design as individual slides)

### X / Twitter
- **Post image:** 1200 × 675px (16:9) or 1200 × 1200px (1:1)
- **Header banner:** 1500 × 500px
- **Card image:** 1200 × 628px

### General
- If the user doesn't specify a platform, default to **1080 × 1080px** (works everywhere)
- For carousels, create numbered files: `slide-1.html`, `slide-2.html`, etc.

---

## Design Principles for Social

### 1. The Thumb-Stop Test

Someone is scrolling at speed. Your visual has ~1.5 seconds to make them pause. This means:

- **One dominant visual element** — not five things competing
- **High contrast** — dark on light or light on dark, bold enough to read on a phone at arm's length
- **Large text** — if there's text, it should be readable at 40% zoom. Social is consumed small
- **Visual tension** — something unexpected, asymmetric, or bold enough to break the scroll pattern

### 2. Less Text, More Impact

Social visuals are not documents. Rules of thumb:

- **Maximum 15 words** visible on any single post/slide
- Headlines: 3-7 words maximum
- If you need more text, it goes in the caption, not the image
- Exception: carousel slides can carry more text per slide since the format invites reading

### 3. Typography IS the Design

On social, type often IS the visual. Make it count:

- Use dramatic size contrast — massive headline, tiny attribution
- Tight letter-spacing on display text (-0.03 to -0.06em)
- Consider text as shape — how the words form a block, how negative space flows around them
- Monospace, handwritten, or display fonts can add personality
- Weight variation creates hierarchy without color

### 4. Color That Pops

Social feeds are noisy. Your visual competes with everything else on screen:

- Bold, saturated colors tend to outperform muted palettes
- Dark backgrounds make content feel premium and high-contrast
- Gradients add dimension — but use 2-3 colors max, not rainbows
- One accent color for emphasis. Don't spray color everywhere
- Test mentally: would this stand out in a feed of selfies and food photos?

### 5. Visual Hierarchy in a Small Space

Even at 1080px, you have limited real estate:

- One clear focal point
- Supporting elements stay small and secondary
- Whitespace is your friend — don't fill every pixel
- Alignment matters more at small sizes — misalignment is jarring

---

## Content Type Patterns

### Quote / Statement
- Large text centered or off-center
- Minimal decoration — let the words breathe
- Attribution in small text, different weight
- Background: solid color, subtle gradient, or textured

### Data / Statistic
- One big number as the hero
- Context in smaller text below
- Optional: simple chart or visual representation (SVG bar, ring, etc.)
- The number should be readable from across a room

### Announcement / Launch
- Product name or feature name bold and large
- Short descriptor underneath
- Optional: mini product UI mockup in CSS/SVG
- Badge or tag ("New", "Now Live", version number)
- CTA-like element even though it's an image ("Try it →", "Link in bio")

### Carousel / Multi-slide
- Slide 1: Hook — bold statement or question that makes them swipe
- Middle slides: Content — one idea per slide, clear progression
- Final slide: CTA — what to do next, follow, link in bio, etc.
- Visual consistency across slides — same background, type system, color palette
- Slight variation to reward swiping — background color shifts, element positions change

### Tutorial / How-to
- Step numbers prominent
- One step per slide in carousels
- Code blocks styled if technical content
- Before/after if showing a transformation

### Behind-the-scenes / Personal brand
- More casual, less polished — intentionally
- Handwritten-style fonts or organic shapes
- Warm colors, less corporate
- Feels human, not branded

---

## Technical Standards

### Single-File HTML

Every visual is one self-contained `.html` file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=1080">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    html, body {
      width: 1080px;
      height: 1080px; /* or target dimensions */
      overflow: hidden;
    }
    /* ... all styles ... */
  </style>
</head>
<body>
  <!-- ... content ... -->
</body>
</html>
```

### No External Dependencies

- Google Fonts are OK (via `<link>` tag)
- No external images — use CSS gradients, SVG, Unicode, or emoji
- No JavaScript required (static visuals) — but light JS is fine for animated visuals the user might want to screen-record

### Font Loading

Social visuals depend heavily on typography. Always include a Google Fonts link for the typeface you choose. Good social fonts:

- **Inter** — clean, professional, works everywhere
- **Space Grotesk** — geometric, modern, techy
- **Sora** — rounded, friendly, approachable
- **DM Sans** — clean, slightly warm
- **JetBrains Mono** — technical, developer audience
- **Playfair Display** — editorial, sophisticated
- **Bricolage Grotesque** — distinctive, characterful

### SVG for Illustrations

Build simple illustrations, icons, and decorative elements in inline SVG:
- Logo marks and icons
- Abstract shapes and patterns
- Simple charts and data visualizations
- Decorative lines and dividers

### CSS for Everything Else

- Gradients for backgrounds and text effects (`background-clip: text`)
- `border-radius` for organic shapes
- `box-shadow` and `filter: blur()` for depth and glow
- `transform` for rotation, scale, and visual interest
- Grid and flexbox for precise layout

---

## Delivery

### Single posts
Output one `.html` file named descriptively (e.g., `launch-announcement-ig.html`).

### Carousels
Output numbered files: `carousel-slide-1.html`, `carousel-slide-2.html`, etc. All slides share the same design system — consistent colors, fonts, spacing.

### Multiple platforms
If the user wants the same content for multiple platforms, create separate files sized for each (e.g., `post-instagram.html` at 1080×1350 and `post-linkedin.html` at 1200×627). Adapt the layout to fit each aspect ratio — don't just scale.

After building, verify:
- [ ] Dimensions match the target platform exactly
- [ ] Text is readable at 50% zoom (simulates phone viewing)
- [ ] No external images — all visuals are CSS/SVG
- [ ] One clear focal point exists
- [ ] Maximum 15 words visible (unless carousel)
- [ ] The visual would stop your thumb in a feed
