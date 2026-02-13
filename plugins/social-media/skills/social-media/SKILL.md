---
name: social-media
description: Create social media visuals as single-file HTML - posts, stories, carousels, banners, and cards for Instagram, LinkedIn, X/Twitter, and other platforms. Use this skill whenever the user asks for a social media post, social graphic, story, carousel, banner, cover image, Open Graph image, promotional visual, quote card, announcement graphic, or any visual content meant for social platforms.
---

This skill creates social media visuals as self-contained HTML files. These can be screenshotted or converted to images for posting on any platform.

## When to Use

Trigger this skill when users ask for:
- Social media posts or graphics
- Instagram posts, stories, reels covers
- LinkedIn posts, banners, cover images
- X/Twitter posts, header images
- Facebook posts, event covers
- Quote cards, announcement graphics
- Promotional visuals
- Open Graph (OG) images
- Carousel slides
- "Make me a post about..."
- "Create a visual for..."
- "Design a graphic for..."

**NOT for**: Landing pages, app interfaces, dashboards (use other skills).

## Platform Dimensions

### Instagram
- **Post (Square)**: 1080 x 1080px
- **Post (Portrait)**: 1080 x 1350px
- **Story**: 1080 x 1920px
- **Carousel**: 1080 x 1080px per slide

### LinkedIn
- **Post**: 1200 x 1200px (square) or 1200 x 628px (landscape)
- **Banner**: 1584 x 396px
- **Profile Cover**: 1128 x 191px

### X/Twitter
- **Post**: 1200 x 675px or 1200 x 1200px
- **Header**: 1500 x 500px

### Facebook
- **Post**: 1200 x 630px
- **Event Cover**: 1920 x 1005px

### Open Graph
- **OG Image**: 1200 x 630px

## Design Principles

### Visual Impact
- **Bold, readable text**: Large enough to read on mobile feeds.
- **High contrast**: Stand out in crowded timelines.
- **Single focal point**: One clear message per visual.
- **Brand consistency**: Colors, fonts, and style that match the brand.

### Typography for Social
- **Headlines**: 48-120px depending on format.
- **Body text**: 24-36px minimum for readability.
- **Font weights**: Bold headlines, medium body.
- **Max 3 text elements**: Headline, subhead, CTA/hashtag.

### Color Strategy
- **Brand colors**: Primary + accent for consistency.
- **Gradient backgrounds**: Modern, eye-catching.
- **Solid overlays**: On photos for text readability.
- **Dark mode friendly**: Consider how it looks on dark feeds.

### Layout Patterns
- **Centered focus**: Text in the center or lower third.
- **Asymmetric balance**: Visual interest through offset elements.
- **Safe zones**: Keep key content away from edges (especially stories).
- **Visual hierarchy**: What should they see first, second, third?

## Technical Implementation

### HTML Structure
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      width: 1080px;
      height: 1080px;
      font-family: 'Inter', system-ui, sans-serif;
    }
    .container { /* your design */ }
  </style>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
</head>
<body>
  <div class="container">
    <!-- Content -->
  </div>
</body>
</html>
```

### Background Techniques
```css
/* Gradient */
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);

/* Mesh gradient */
background:
  radial-gradient(at 30% 20%, #ff6b6b 0%, transparent 50%),
  radial-gradient(at 70% 80%, #4ecdc4 0%, transparent 50%),
  linear-gradient(135deg, #1a1a2e, #16213e);

/* Noise texture overlay */
.noise::after {
  content: '';
  position: absolute;
  inset: 0;
  background: url("data:image/svg+xml,...") repeat;
  opacity: 0.1;
  pointer-events: none;
}
```

### Text Effects
```css
/* Gradient text */
.gradient-text {
  background: linear-gradient(90deg, #fff, #a5b4fc);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* Text shadow for depth */
.shadow-text {
  text-shadow: 0 4px 30px rgba(0,0,0,0.3);
}
```

## Content Types

### Quote Cards
- Large quote text (60-80px)
- Attribution smaller below
- Decorative quote marks
- Solid or gradient background

### Announcement Posts
- Clear headline
- Key details in bullet/icon format
- CTA or date prominently displayed
- Brand colors and logo placement

### Carousel Slides
- Consistent template across slides
- Clear slide numbering or progress
- Hook on first slide
- CTA on last slide

### Story Graphics
- Full-bleed design
- Large, centered text
- Swipe-up or link CTA zone at bottom
- Animated elements if desired

## Output

Deliver a complete HTML file that:
1. Has exact dimensions for the target platform
2. Is self-contained (inline CSS, no external images)
3. Uses web fonts from Google Fonts
4. Is ready to screenshot or convert to PNG/JPG
5. Looks professional and on-brand
