# /system/ — Shared System Files

Everything in this folder is brand-agnostic and shared across all clients. Templates, frameworks, and rules that power the ad production pipeline.

## Folder Structure
```
system/
├── README.md               ← You are here
├── templates/              ← Prompt templates for image generation
│   ├── avatar-cast.json
│   ├── scene-expression.json
│   ├── product-integration-frame-a.json
│   ├── frame-b.json
│   └── veo-interpolation.json
├── frameworks/             ← Business logic and processes
│   ├── brand-onboarding.json
│   ├── concept-generator.json
│   ├── hook-types.json
│   └── script-structures.json
└── rules/                  ← Production-tested rules
    └── v5-lessons.json
```

---

## /templates/ — Image Generation Prompts

These are the prompt templates used at each stage of the image generation pipeline. Fill in `[FILL]` fields with brand/product/character specifics.

**Use them in order:**

| Stage | Template | What It Does | Reference Images |
|-------|----------|-------------|-----------------|
| 1 | `avatar-cast.json` | Generate character, neutral expression. Lock the face | None (generating new) |
| 2 | `scene-expression.json` | Put character in scene + expression. No product | Character ref |
| 3 | `product-integration-frame-a.json` | Add product. This is Frame A | Character ref + Product ref |
| 4 | `frame-b.json` | Generate ending frame from Frame A | Frame A output ONLY |
| 5 | `veo-interpolation.json` | Animate between frames | Frame A + Frame B |

**Rules for templates:**
- Always JSON structure, never flat paragraphs
- Expression at 30% intensity (models amplify)
- Gaze 2-3° off camera axis
- Deep DOF always (no portrait mode blur)
- Products from reference images only, never text descriptions
- Frame B uses ONE reference (Frame A), not separate product image

---

## /frameworks/ — Business Logic

### brand-onboarding.json
The full 13-step process for onboarding a new client. From website scrape to completed brand vault with star product identified. Follow this when user says "onboard [brand]."

### concept-generator.json
How to generate ad concepts. Matches product ad angles × hook types × audience pain points to produce 10-15 concepts with confidence ratings. Includes scoring criteria and approval workflow.

### hook-types.json
8 proven UGC hook frameworks:
1. **Shocked Discovery** — "wait, is this actually working?" ✅ TESTED
2. **Skeptic to Believer** — conversion arc
3. **Secret Share** — conspiratorial insider knowledge
4. **Mind Blown** — information revelation ✅ TESTED
5. **Morning Routine** — daily life integration
6. **Problem → Agitate → Solve** — pain point to solution
7. **Before/After (Subtle)** — believable change
8. **Unboxing / First Impression** — demystifying the product

Each has emotional arc, best-for categories, text overlay examples, and frame sequences.

### script-structures.json
Beat templates for 3 ad lengths:
- **3 seconds** — Hook only (scroll stopper)
- **15 seconds** — Full ad (hook + body + CTA)
- **30 seconds** — Story ad (hook + problem + solution + proof + CTA)

Includes script writing rules (hook works without audio, one claim per beat, etc.)

---

## /rules/ — Battle-Tested Production Rules

### v5-lessons.json
12 rules, each with the specific failure that created it. Categories:
- **Pipeline rules** — staging, ordering, character-first
- **Prompting rules** — JSON format, expression intensity, gaze direction, signature details
- **Product rules** — reference images only, physical dimensions, scale consistency between frames
- **Reference image rules** — Frame B single reference, phone visibility

Also contains the **negative prompt library** organized by category (optical fakes, lighting fakes, skin fakes, composition fakes, product fakes, phone fakes, expression fakes).

---

## Adding to the System

### New template
Add to `/templates/`. Follow the existing structure with `[FILL]` placeholders. Include `_template`, `_version`, `_description`, `_usage` metadata fields.

### New hook type
Add to `hook-types.json` in the `hooks` object. Include name, description, emotional arc, duration, best-for, text overlay examples, frame sequence, tested flag.

### New rule
Add to `v5-lessons.json`. Every rule MUST have: id, rule, failure (what went wrong), enforcement (how it's prevented). Rules only come from actual production failures, not theory.
