# 05 — Batch Workflow

## Creating Avatar Sets for Brands

When a brand needs multiple avatars (3-5 per campaign), follow this workflow.

## Step 1: Define the Buyer

Before generating:
- Who buys this product? (age range, gender split, lifestyle)
- What do they ACTUALLY look like? (not aspirational)
- Where would they take a selfie? (→ lighting scenario)
- What are they wearing on a random Tuesday?

## Step 2: Pick Archetypes + Lighting

Choose 3-5 from `02-ARCHETYPES.md`. Pair each with a lighting scenario from `03-LIGHTING-LIBRARY.md`. Ensure variety:

| Dimension | Vary Across Set |
|---|---|
| Age | Spread across brand's real age range |
| Gender | Match brand's actual gender split |
| Ethnicity | Represent real customer base |
| Build | Realistic variety |
| Lighting | Different scenario for each avatar |
| Expression | Different FACS configuration each time |
| Environment | Different room/setting per avatar |

## Step 3: Generate

For each avatar:
1. Copy the archetype template from `02-ARCHETYPES.md`
2. Swap in the specific person details
3. Swap in the lighting block from `03-LIGHTING-LIBRARY.md`
4. Generate 3 variations
5. Pick the most natural one

## Step 4: Quality Gate

For EACH avatar:
- [ ] Has `<thought_process>` block?
- [ ] iPhone camera forensics (23mm, infinite DOF, barrel distortion)?
- [ ] Skin uses clinical terms (not "beautiful" or "glowing")?
- [ ] Expression is FACS-based at ≤30%?
- [ ] Gaze is 7° down at phone screen?
- [ ] Selfie arm creates shoulder/torso asymmetry?
- [ ] Catchlights are rectangular?
- [ ] Background has realistic clutter?
- [ ] Negatives use semantic exclusion JSON?

**If 2+ checks fail → regenerate from scratch.**

## Step 5: Name & Save

```
[brand]-[archetype]-[number].jpg

Examples:
ag1-optimizer-01.jpg
seed-wellness-mom-02.jpg
ritual-glow-up-01.jpg
```

## Batch Size Guide

| Campaign Scale | Avatars Needed |
|---|---|
| Test batch (5-10 ads) | 3 avatars |
| Growth (20-30 ads) | 5 avatars |
| Scale (50+ ads) | 5-8 avatars, rotate in batches |
