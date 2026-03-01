# 08 — Image Prompt Guide (V5 JSON System)

## Core Rule: Always Use JSON Prompts

**Never write flat paragraph prompts.** Every image generation prompt uses structured JSON from the templates in `system/templates/`. This gives precise control over every element and makes failures diagnosable.

## The 4-Stage Pipeline

Generate images in stages. Never skip ahead.

```
Stage 1: CHARACTER CAST → neutral expression, no scene, no product
Stage 2: SCENE + EXPRESSION → character in environment with emotion, no product
Stage 3: PRODUCT INTEGRATION (Frame A) → character + product + scene + expression
Stage 4: FRAME B → expression change ONLY, from Frame A reference
```

### Why Stages Matter
If you combine everything in one prompt and it looks wrong, you can't tell what failed — was it the character, the expression, the product placement, or the scene? Stages isolate variables.

## Templates (in `system/templates/`)

| Template | Stage | File | Use When |
|----------|-------|------|----------|
| Avatar Cast | 1 | `avatar-cast.json` | Creating/locking a new character |
| Scene Expression | 2 | `scene-expression.json` | Testing character in a scene with emotion |
| Product Integration A | 3 | `product-integration-frame-a.json` | Adding product to scene (Frame A) |
| Frame B | 4 | `frame-b.json` | Expression change from Frame A |
| Veo Interpolation | — | `veo-interpolation.json` | Animating Frame A → B into video |

## How to Use a Template

1. Open the template JSON
2. Fill every `[FILL: ...]` field using data from:
   - `brand.json` — brand colors, tone
   - `avatar.json` or `cast-prompt.json` — character details
   - `product.json` — product physical specs
   - Script file — what's happening in this shot
3. Attach the specified reference images
4. Paste the filled JSON as your generation prompt

## Critical Rules (Battle-Tested)

These are from `system/rules/v5-lessons.json` — every one learned from a real failure:

1. **Script BEFORE images.** Always write the script first
2. **Expression at 30% intensity.** What you think is subtle is still too much
3. **Gaze 2-3° off-camera.** Dead-center = AI-looking. Slightly off = selfie-authentic
4. **Products from reference images ONLY.** Never describe products in text — attach a photo
5. **Frame B uses ONLY Frame A as reference.** One image, not two
6. **5 fingers. Always specify.** AI hands fail without explicit instruction
7. **Signature details on every character.** 2-3 unique identifiers (scars, streaks, asymmetry) that you verify in every generation
8. **Deep DOF, no blur.** iPhone selfies use deep focus. Portrait mode blur = instant AI tell
9. **Product scale must match between frames.** Specify physical dimensions

## Avatar System

Each brand has avatars in `brands/[brand]/avatars/`. An avatar includes:

- **avatar.json** — Full character spec with signature details, physical description, styling, expression asymmetry, and a reusable `prompt_block`
- **reference.jpg** — The locked character image (generated from cast template, saved here)
- **cast-prompt.json** — The original casting prompt (for re-casting if needed)

### Character Consistency
The key to consistent characters across shots:
1. Cast with neutral expression (Stage 1)
2. Define 3 signature details (primary/secondary/tertiary)
3. Include verification checks: "Is the grey streak visible? If not, regenerate"
4. Always attach reference.jpg to every subsequent prompt
5. Copy `prompt_block.avatar_reference_instruction` into every prompt

## Production Boards

The final output for each ad is a **production board** (`shots/[ID]-production-board.json`). This contains:

- Ad metadata (duration, format, hook line, avatar, product)
- Visual storyboard (second-by-second)
- Shot-by-shot JSON prompts ready to paste into image gen
- Reference image chains (which output feeds into which input)
- Text overlays per shot

Production boards are the handoff document — everything needed to generate the complete ad.

## Negative Prompts

Always include negative prompts. Common ones for UGC-style:
- `background blur`, `bokeh`, `portrait mode`
- `studio lighting`, `ring light`, `perfect skin`
- `airbrushed`, `beauty mode`, `symmetrical face`
- `model pose`, `stock photo`
- `phone visible in frame`
- Plus character-specific negatives (e.g., "missing chin scar")
