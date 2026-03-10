# 04 — Batch Workflow

## Creating Avatar Sets for Brands

When a brand needs multiple avatars (3-5 per campaign), use this workflow to ensure variety and quality.

## Step 1: Define the Audience

Before generating anything, answer:
- Who buys this product? (age range, gender split, lifestyle)
- What do they look like in real life? (not aspirational — actual)
- Where would they take a selfie? (context for lighting + environment)
- What are they wearing on a random Tuesday?

## Step 2: Pick Archetypes

Choose 3-5 from `02-ARCHETYPES.md` or create custom ones. Ensure variety across:

| Dimension | Vary Across Set |
|-----------|----------------|
| Age | Spread across the brand's actual age range |
| Gender | Match the brand's actual gender split |
| Ethnicity | Represent the real customer base |
| Build | Realistic variety — not all athletic, not all slim |
| Lighting | Different for each (window, outdoor, ambient, overcast) |
| Expression | Never the same twice (neutral, slight smile, mid-thought, surprised) |
| Environment | Different rooms/settings per avatar |

## Step 3: Generate

For each avatar:
1. Write the full prompt following the SYSTEM-PROMPT structure
2. Generate 3 variations
3. Pick the most natural-looking one (apply the quality gate)
4. If none pass the quality gate, revise the prompt and regenerate

## Step 4: Quality Gate

For EACH generated avatar, check:

- [ ] Passes as a real iPhone selfie at first glance?
- [ ] Skin has visible pores and texture?
- [ ] No ring light circles in eyes?
- [ ] Hair looks naturally styled/messy (not salon-perfect)?
- [ ] Expression is subtle and genuine?
- [ ] Clothing has real wear (wrinkles, fading)?
- [ ] Background is simple and natural?
- [ ] No visible hands or fingers?
- [ ] Gaze is slightly off-center?

**If 2+ checks fail → regenerate, don't try to fix it.**

## Step 5: Save

Name files clearly:
```
[brand]-[archetype]-[number].jpg
```
Examples:
```
ag1-optimizer-01.jpg
seed-wellness-mom-02.jpg
ritual-glow-up-01.jpg
```

## Batch Size Guidelines

| Campaign Scale | Avatars Needed | Why |
|---|---|---|
| Test batch (5-10 ads) | 3 avatars | Enough variety without overproduction |
| Growth campaign (20-30 ads) | 5 avatars | Covers audience segments, prevents fatigue |
| Scale campaign (50+ ads) | 5-8 avatars | Rotate in batches to keep ads fresh |

## Diversity Without Tokenism

Real brands sell to real people. Diversity in avatars should reflect the actual customer base:

- **Look at the brand's existing customers** — social media, reviews, testimonials
- **Match the demographic reality** — a luxury collagen brand and a mass-market multivitamin have different customer bases
- **Avoid stereotyping** — don't put every Asian avatar in a minimalist setting or every Black avatar in athleisure
- **Each person is an individual** — vary styling, expression, and environment within each demographic
