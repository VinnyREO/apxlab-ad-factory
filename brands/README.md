# /brands/ — Client Brand Vaults

Each subfolder is one client. Contains everything needed to produce ads for that brand.

## Brand Folder Structure
```
[brand-name]/
├── brand.json              ← Brand identity, voice, colors, positioning
├── products/               ← One JSON + images per product
│   ├── [product].json      ← Claims, pricing, packaging, ad angles
│   └── [product]-front.jpg ← Product reference image (REQUIRED for image gen)
├── audience/               ← Target persona files
│   └── persona-[name].json ← Demographics, pain points, what converts them
├── avatars/             ← Locked AI-generated avatars
│   └── [character-name]/
│       ├── character.json  ← Signature details, locked features, prompt block
│       └── reference.jpg   ← Locked neutral-expression reference image
└── campaigns/              ← Ad campaigns (one per launch/sprint)
    └── [campaign-name]/
        ├── concepts.json   ← Generated concepts with approval status
        ├── scripts/        ← Beat-by-beat scripts for approved concepts
        ├── shots/          ← Prompts (.json) and generated images (.jpg)
        ├── output/         ← Final edited ad videos (.mp4)
        └── performance/    ← Post-launch metrics (feeds back into concepts)
```

## Key Files Explained

### brand.json
Brand identity. Voice/tone, visual identity, key differentiators, competitive landscape, social proof. Informs how every ad sounds and feels.

### products/[product].json
Product details including **pricing** (DTC, insurance), **packaging** (dimensions, material, colors, scale-in-hand), **reference images**, **key claims**, and **ad angles** (hooks, proof points, emotional triggers).

Critical for image gen: `packaging.scale_in_hand` and `reference_images`.

### audience/persona-[name].json
Target persona. Pain points, what converts them, objections + counters, character match guidelines.

### avatars/[name]/character.json
Locked avatar with **signature details** (visual fingerprints: moles, scars, gaps), expression asymmetry, default styling, and `prompt_block.character_reference_instruction` — the exact text to paste into prompts.

### campaigns/concepts.json
Ad concepts with hook type, angle, confidence rating, approval status. Approved concepts link to script files.

### campaigns/scripts/script-[id].json
Second-by-second scripts with shot lists. Each shot specifies which template to use and which reference images to attach.

## Adding a New Brand
Follow `/system/frameworks/brand-onboarding.json` (13-step process) or manually create the structure and fill the files.
