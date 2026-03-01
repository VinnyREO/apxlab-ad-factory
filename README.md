# APXlab Ad Factory — Knowledge Base

This repository contains the knowledge files for the **Ad Factory** Claude Project by [APXlab](https://apxlab.com).

## What is this?

A structured knowledge base that powers an AI-driven ad creation system. These files are uploaded as **Project Knowledge** in Claude Projects, enabling Claude to generate high-converting direct-response video ad scripts, storyboards, image prompts, and production-ready JSON prompt boards.

## Files

### Knowledge Docs (Markdown)
| File | Description |
|------|-------------|
| `02-AD-FRAMEWORKS.md` | Core advertising frameworks (PAS, AIDA, BAB, etc.) |
| `03-HOOK-FORMULAS.md` | Proven hook formulas for stopping the scroll |
| `04-SCENE-LIBRARY.md` | Visual scene templates for storyboards |
| `05-AVATAR-ARCHETYPES.md` | Customer avatar definitions and targeting |
| `06-STORYBOARD-TEMPLATE.md` | Storyboard structure and formatting |
| `07-SCRIPT-EXAMPLES.md` | Example scripts across niches |
| `08-IMAGE-PROMPT-GUIDE.md` | V5 JSON image prompt system (staged pipeline) |
| `09-PRODUCTION-CHECKLIST.md` | Pre-publish quality checklist |
| `10-COMPLIANCE-REFERENCE.md` | Supplement/health ad compliance rules |
| `11-STATIC-AD-SYSTEM.md` | Static ad template × variation system |

### V5 JSON Prompt System (`system/`)
| Folder | Description |
|--------|-------------|
| `system/templates/` | JSON prompt templates for each pipeline stage (cast, scene, product, frame B, animation) |
| `system/rules/` | Battle-tested rules from production failures |
| `system/frameworks/` | Concept generation, hook types, script structures, brand onboarding |

### Brand Vaults (`brands/`)
| Folder | Description |
|--------|-------------|
| `brands/infinite-allergy-labs/` | Active client — brand.json, products, avatars (Bea, Beth, Emma, Tara), campaigns, audience personas |
| `brands/lyfefuel/` | Demo brand — brand.json, products, avatar (Olive Girl), audience personas |

## Production Pipeline
```
ONBOARD → CONCEPT → SCRIPT → CHARACTER CAST → SCENE TEST → PRODUCT SHOT → FRAME B → ANIMATE → EDIT
   │          │         │         │              │             │             │          │        │
brand.json  10 ideas  beat-by-  neutral face   expression    product in   expression  Veo/    final
products    pick 3-5  beat +    lock identity  + scene test  hand (A)     change (B)  Kling   .mp4
personas              shot list  signature                    from ref                
                                 details                      image
```

## Key Principles
1. **JSON prompts always** — structured fields, not paragraph descriptions
2. **Staged pipeline** — cast → scene → product → frame B (isolate failures)
3. **30% expression** — understate everything, theatrical = AI-looking
4. **Products from reference images** — never text-described
5. **Signature details** — 2-3 unique identifiers per character for consistency
6. **Script before images** — always

## Quick Start

### "Onboard a new brand"
Give the brand URL. System reads `system/frameworks/brand-onboarding.json` and creates the full brand vault.

### "I need 10 ad concepts for [brand]"
Reads brand vault + `system/frameworks/concept-generator.json` + `system/frameworks/hook-types.json`. Outputs concepts matched to product angles × hook types × audience pain points.

### "Write scripts for concepts C001, C004"
Reads concepts + `system/frameworks/script-structures.json`. Writes second-by-second scripts with shot lists.

### "Generate production board for script C001"
Reads script + avatar + product + templates. Outputs a shot-by-shot JSON production board with ready-to-paste prompts for every frame.

## Static Ads
Templates in `static-ad-templates/` — 8 reverse-engineered from winning ads. Combined with `11-STATIC-AD-SYSTEM.md` for mass variation generation (template × 3 visuals × 3 copy angles).
