# 12 — Avatar Generator (Standalone Photorealistic Portraits)

## When to Use This

Use this guide when you need **standalone avatars** — realistic people for ads, brand personas, or creative assets. NOT for full ad production (use the 4-stage pipeline in 08 for that).

**One prompt. One great midshot. Real-looking human.**

## Core Philosophy

The goal is a person who looks like they were photographed, not generated. Strip away everything that screams "AI":

- No signature details system (scars, streaks, asymmetry markers)
- No staged pipeline
- No JSON templates
- No verification checklists

Just a clean, natural-looking person.

## The Midshot Standard

Every avatar uses **midshot framing**: head, shoulders, and upper torso visible. This gives:
- Face for emotional connection
- Upper body for context (clothing, posture, environment)
- Natural "talking to a friend" feel

**Camera specs (baked into every prompt):**
- iPhone front camera, arm's length to chest distance
- Deep depth of field (everything sharp, NO bokeh/blur)
- Gaze 2-3° off-center (not dead into lens)
- Vertical 9:16 or square 1:1

## What Makes Avatars Look AI (Avoid These)

| AI Tell | Fix |
|---------|-----|
| Perfect symmetrical face | Don't specify symmetry. Let the model be natural |
| Waxy/poreless skin | Specify real skin: pores, texture, minor blemishes, uneven tone |
| Ring light catchlights | Use natural window light or ambient light only |
| Portrait mode blur | Deep DOF always. Everything in focus |
| Dead-center eye contact | Gaze slightly off-camera (2-3°) |
| Over-styled hair | Specify "day-two hair" or "natural unstyled" |
| Too-clean clothing | Include subtle wear: wrinkles, fading, real fabric texture |
| Perfect teeth in smile | Don't over-specify teeth. Natural smiles aren't perfect |
| Overly dramatic expression | Dial expression to 30% of what you imagine |
| Hands/fingers visible | Crop above hands OR specify "5 fingers" explicitly |
| "Influencer posing" | Natural posture, slight slouch, relaxed shoulders |
| Uniform studio lighting | Mixed natural light with subtle shadows |

## Prompt Structure

Write prompts as natural descriptions. No JSON needed. Include these elements in this order:

```
1. PERSON: Age, gender, ethnicity, build — keep it natural and brief
2. FACE & SKIN: Real skin with texture. Mention what makes them human (pores, under-eye warmth, uneven skin tone, facial hair texture, laugh lines)
3. HAIR: Specific but natural. Day-two hair > freshly styled. Include texture and state
4. EXPRESSION: Subtle. 30% intensity. What would their face look like mid-conversation?
5. CLOTHING: Real, worn-in clothes. Wrinkles, fading, pilling. Match to their life context
6. FRAMING: Midshot — head, shoulders, upper chest. Arm's length selfie distance
7. LIGHTING: Natural light. Window light, outdoor shade, ambient room light. Never studio
8. ENVIRONMENT: Simple background that matches who they are. Home, kitchen, gym, outdoors
9. CAMERA: iPhone front camera, deep DOF, no portrait mode, no blur
10. NEGATIVE: No bokeh, no studio lighting, no airbrushed skin, no ring light, no beauty filter
```

## Example Prompts by Archetype

### The Busy Mom (Supplements, Wellness, Sleep)
```
Candid midshot selfie of a real woman, early-mid 30s, warm olive skin with visible pores and slight under-eye warmth, natural laugh lines beginning to form, dark brown wavy hair pulled back in a loose messy bun with flyaways, subtle tired but genuine half-smile like she just sat down for the first time today, wearing an oversized heather grey crewneck sweatshirt with slight pilling at the cuffs, relaxed rounded shoulders, shot from chest up at arm's length selfie distance, soft warm morning window light from the left casting gentle shadow on right side of face, simple kitchen background slightly out of focus with open shelving, iPhone front camera, deep depth of field, everything in focus, gaze looking 2 degrees right of camera lens with soft unfocused warmth. No bokeh, no portrait mode, no beauty filter, no studio lighting, no ring light, no airbrushed skin, no perfect symmetry, no phone visible in frame.
```

### The Biohacker / Fitness Guy (Performance, Protein, Pre-Workout)
```
Candid midshot selfie of a real man, late 20s, light brown skin with visible pores and natural shine on forehead, slight stubble shadow along jawline with a few uneven patches, short dark hair with natural texture slightly mussed up, subtle confident expression — not smiling but not stern, like mid-thought after a workout, wearing a worn-in dark navy performance tee with faded collar, athletic but not bodybuilder build visible in shoulders, shot from chest up at arm's length selfie distance, natural bright daylight from a window behind camera creating even face lighting with warm undertones, plain apartment wall background with a glimpse of a shelf edge, iPhone front camera, deep depth of field, gaze 3 degrees left of lens with calm energy. No bokeh, no blur, no studio lighting, no ring light catch lights, no beauty mode, no airbrushed skin, no overly dramatic expression, no hands in frame.
```

### The Wellness Seeker (Greens, Gut Health, Daily Vitamins)
```
Candid midshot selfie of a real woman, late 20s, fair skin with light freckles across nose and cheeks, visible pore texture on chin and forehead, natural slight pink in cheeks, light auburn hair in a relaxed natural part falling past shoulders with some frizz at the crown, soft genuine smile at about 30% — lips together with slight upward curve at corners, wearing a slightly wrinkled sage green linen button-up with top button undone, relaxed posture with one shoulder slightly higher than the other, shot from chest up at arm's length, soft diffused overcast daylight from a nearby window creating flat even lighting with no harsh shadows, simple bright room background with a plant edge visible, iPhone front camera, deep depth of field, looking just barely past the camera lens to the right. No bokeh, no portrait blur, no ring light, no beauty filter, no studio lighting, no perfect skin, no symmetrical pose, no hands visible.
```

### The Skeptic-Turned-Believer (Testimonial Angle, Any Product)
```
Candid midshot selfie of a real man, early 40s, medium brown skin with natural texture and visible laugh lines around eyes, slight grey at temples in short cropped hair, day-old stubble with some grey mixed in, expression of genuine pleasant surprise — subtle raised eyebrows and slight open-mouth smile like he's about to say "honestly I didn't expect it to work", wearing a lived-in charcoal henley with slightly stretched collar, natural build with relaxed shoulders, shot from chest up at arm's length selfie distance, warm indoor ambient lighting mixed with some window light creating natural mixed shadows, kitchen or living room background slightly visible, iPhone front camera, deep depth of field, gaze direction 2 degrees off-center to the left. No bokeh, no blur, no airbrushed skin, no studio lighting, no ring light, no beauty mode, no hands, no phone visible.
```

### The Radiant Minimalist (Collagen, Beauty, Skin Health)
```
Candid midshot selfie of a real woman, mid-20s, rich dark brown skin with natural glow and visible pore texture especially on cheeks and nose, dark coily hair in a natural pineapple updo with some edges visible, subtle knowing smile with lips slightly parted — confident but not posed, wearing a simple cream ribbed tank top with natural wrinkles, delicate thin gold chain necklace, relaxed natural posture, shot from chest up at arm's length, bright natural daylight from a window to the left creating a warm highlight on one cheek with soft shadow on the other, simple bright bathroom or bedroom background, iPhone front camera, deep depth of field, eyes looking just barely above the camera lens with warm relaxed energy. No bokeh, no portrait mode, no beauty filter, no studio lighting, no ring light catch lights, no airbrushed skin, no perfect symmetry, no hands in frame.
```

## Customizing for a Brand

When creating avatars for a specific brand:

1. **Check the brand folder** — `brands/[brand]/` for audience personas, product info, brand colors
2. **Match the avatar to the ICP** — the person in the image should look like the BUYER, not a model
3. **Clothing colors** can subtly echo brand palette — but keep it natural (a shirt in a similar tone, not branded merch)
4. **Environment should match the product context** — gut health product? Kitchen. Pre-workout? Near a gym bag. Sleep supplement? Bedroom, evening light
5. **Age and life stage matter** — a 45-year-old dad buying joint supplements looks different from a 25-year-old buying pre-workout

## Batch Generation Tips

When creating multiple avatars for one brand:

- **Vary demographics** across age, gender, ethnicity, build — represent the actual customer base
- **Vary lighting** — not every avatar needs window light. Try overcast outdoor, ambient evening, bright morning
- **Vary expressions** — some neutral, some subtle smile, some mid-conversation. Never the same expression twice
- **Keep clothing realistic** to the archetype — a parent wears loungewear, a gym person wears athletic wear
- **Generate 3 per archetype** and pick the most natural-looking one. Discard anything with AI tells

## Quality Check

Before accepting a generated avatar, verify:

- [ ] Could this be a real iPhone selfie? (If not, regenerate)
- [ ] Skin has texture, pores, imperfections?
- [ ] No ring light circles in eyes?
- [ ] Hair looks naturally messy/styled, not "AI perfect"?
- [ ] Expression feels genuine, not posed?
- [ ] Clothing has wrinkles, texture, wear?
- [ ] Background is simple and natural?
- [ ] No hands or fingers visible (unless explicitly wanted)?
- [ ] Gaze is slightly off-center?

If any check fails, add the specific fix to the negative prompt and regenerate.

## Using Avatars in the Full Ad Pipeline

Once you have a great standalone avatar, you can bring it INTO the 4-stage pipeline:

1. Save the generated image as the character's `reference.jpg`
2. Use it as the reference image in Stage 2+ prompts
3. Skip the formal avatar-cast.json process — your standalone portrait IS the cast

This bridges standalone avatar generation with the full ad production system.
