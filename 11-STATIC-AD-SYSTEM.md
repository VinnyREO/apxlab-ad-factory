# Static Ad System — Mass Production Guide

## How It Works
When asked to create static ads, use templates from `static-ad-templates/` combined with brand data from `brands/[name]/`.

## Generating Statics

### Input
User provides: brand name (must have a brand folder) + number of statics desired + optional template preferences.

### Output Per Static
1. **Image generation prompt** — complete, copy-paste ready, includes brand colors, product description, layout
2. **Primary copy** — headline + body + CTA
3. **Text overlay specs** — what text goes ON the image, position, size, color

### Variation System
For each template, generate **3 visual variations**:
- **Variation A (Brand Primary):** Uses primary brand color as background/accent
- **Variation B (Dark/Contrast):** Dark background, light text, premium feel
- **Variation C (Light/Clean):** White/cream background, minimal, modern

And **3 copy angles** per variation:
- **Angle 1: Pain Point** — leads with the problem
- **Angle 2: Social Proof** — leads with reviews/stats/authority
- **Angle 3: Offer/CTA** — leads with the deal/discount

This means: 1 template × 3 visuals × 3 copy angles = **9 unique statics**.

### Batch Commands
- **"5 statics for [brand]"** → Pick 5 best templates, 1 variation each = 5 statics
- **"Full batch for [brand]"** → All 8 templates × 3 variations = 24 statics
- **"Spec statics for [brand]"** → 3-5 best templates, designed as free samples for cold outreach

### Brand Asset Integration
When generating prompts, ALWAYS reference the brand's `brand-assets.md`:
- Use exact hex colors in the prompt (e.g., "background color #2D5F3E")
- Reference product images by description from the scraped data
- Match font style (serif/sans-serif/modern/traditional)
- Include actual product name and pricing in copy
- Use real social proof stats if available

### Image Prompt Format for Statics
```
[LAYOUT]: [Template name] format, [aspect ratio]
[BACKGROUND]: [Color/gradient using brand hex codes]
[PRODUCT]: [Detailed product description — shape, color, label, packaging]
[TEXT ZONES]:
  - Header: "[Headline text]" in [font style], [color], [position]
  - Subhead: "[Body text]" in [font style], [color], [position]
  - CTA: "[CTA text]" in [button/banner style], [color]
[ELEMENTS]: [Trust badges, star ratings, icons, decorative elements]
[STYLE]: Professional ad creative, clean layout, high contrast text, commercial quality
[SIZE]: 1080x1080 (square) or 1080x1350 (4:5 portrait)
```

### For Cold Email Spec Ads
When creating statics for outreach prospects:
1. Use the prospect's actual product images/colors (from brand scrape)
2. Pick 3-5 templates that fit their niche best
3. Make them look premium — these are the first impression
4. Include competitor-inspired angles (show you understand their market)
5. One variation per template is enough (don't overwhelm)
6. Output should be: prompt + copy, ready to generate and attach to email

### Platform Sizing
| Platform | Size | Aspect Ratio |
|----------|------|-------------|
| Facebook/Instagram Feed | 1080x1080 | 1:1 |
| Instagram Feed (optimal) | 1080x1350 | 4:5 |
| Facebook Feed (optimal) | 1200x628 | 1.91:1 |
| Stories/Reels | 1080x1920 | 9:16 |
| Pinterest | 1000x1500 | 2:3 |

Default to **1080x1080** (works everywhere) unless specified.
