# /avatars/ — AI-Generated Brand Avatars

Each subfolder is one locked avatar. A brand can have multiple avatars for different personas, demographics, or ad angles.

## Structure
```
avatars/
├── README.md              ← You are here
├── catalog.json           ← Master list of all avatars with status and persona match
├── bea/
│   ├── avatar.json        ← Locked identity details, signature features, prompt block
│   └── reference.jpg      ← THE locked neutral reference image
├── [next-avatar]/
│   ├── avatar.json
│   └── reference.jpg
└── ...
```

## Avatar Naming Convention
- Use short memorable first names (Bea, Tara, Beth, Emma)
- Folder name = lowercase first name
- Keep it simple — these are internal working names, not public

## Avatar Lifecycle
1. **CAST** — Generate using `/system/templates/avatar-cast.json`. Get 3-4 variations
2. **SELECT** — Pick best output. Verify signature details (grey streak? chin scar? brow asymmetry?)
3. **LOCK** — Save as `reference.jpg`. Create `avatar.json` with full details
4. **USE** — Paste `prompt_block.character_reference_instruction` into all scene/product prompts. Attach `reference.jpg`
5. **RETIRE** — If avatar doesn't perform in ads, mark status as RETIRED in catalog.json. Keep files for reference

## When to Create Multiple Avatars
- Different audience personas (e.g. younger vs older demo)
- Different ad angles that need different "looks" (e.g. fitness angle vs medical angle)
- A/B testing avatar performance (does audience respond better to Avatar A or B?)
- Different product lines within same brand

## Rules
- Every avatar MUST have a reference.jpg before being used in scene prompts
- Never use an avatar without checking signature details in the generated output
- One avatar per ad — don't mix avatars within a single ad
- Avatar prompt_block is the source of truth — always copy from avatar.json, never from memory
