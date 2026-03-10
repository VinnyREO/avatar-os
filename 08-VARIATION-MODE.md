# 08 — Variation Mode (Rapid Avatar Swapping)

## The Concept

Once you have ONE good image of a person holding the product correctly, use it as a reference to generate dozens of variations — different people, different settings, same product.

## The Workflow

### Step 1: Get your first good image
Generate (or find) one image where the product looks right — correct size, correct grip, correct label. This becomes your **seed image**.

### Step 2: Feed the seed image back with a variation prompt
Attach the seed image and ask for variations. The model sees the product in context and replicates it while changing the person.

### Step 3: Generate in batches
Each prompt produces a new avatar holding the same product. Run it multiple times for a full set.

## The Variation Prompt

Attach your seed image and use this prompt:

```
Using the attached image as reference for the PRODUCT ONLY — keep the exact same product (same packaging, colors, label, size, grip style) but generate a completely different person.

New person: [describe OR say "random — surprise me"]
New setting: [describe OR say "fitting for this product's context"]

Rules:
- The product must match the attached reference exactly — same packaging, same label, same colors
- The person must be completely different — different age, ethnicity, hair, build, clothing
- Maintain the same candid portrait style and framing as the reference
- The person fills 80% of the frame, product is secondary
- No phone or camera visible in the image
- Shot from arm's length, 23mm wide-angle perspective
- Natural lighting appropriate to the setting
- 9:16 vertical format
```

## Quick Variations (Even Faster)

For rapid-fire variations, use short prompts after your first generation:

**"Same product, different person. Make her a 40-year-old Black woman in a cozy bedroom, evening lighting."**

**"Same product, different person. Make him a 28-year-old guy in a modern bathroom, morning light."**

**"Same product, new avatar. Random person, random setting that fits the product."**

**"Generate 4 different people holding this same product in different settings."**

The seed image anchors the product — the model knows exactly what it looks like, how big it is, and how it's held. You just swap the human.

## Batch Prompt (Multiple Variations at Once)

```
Using the attached image as the product reference, generate 4 different candid portraits of different people holding this exact same product. Each person should be:

1. A different age (20s, 30s, 40s, 50s)
2. A different ethnicity
3. In a different setting appropriate for this product
4. Different clothing, hair, and expression
5. Same candid arm's length portrait style
6. Same product — exact match to the attached reference
7. 9:16 vertical, natural lighting, no phone visible

Make each person feel like a real customer, not a model.
```

## Why This Works

- The model already has the product solved — correct appearance, correct scale, correct grip
- Changing the person is the "easy" variable for the model
- You skip all the product sizing/grip engineering on subsequent generations
- Faster iteration: 1 good seed = unlimited variations
- Natural diversity: different people, settings, lighting = full ad creative set

## Tips

- **Save your best seed image** for each product. It's your master reference.
- **If the product drifts** (changes color, shape, or label), go back to the seed image and re-attach it
- **Mix settings**: bathroom, bedroom, kitchen, living room, outdoor — each setting gives a different ad angle
- **Mix expressions**: some people excited about the product, some casual, some mid-conversation
- **Don't over-specify**: shorter variation prompts often produce more natural results than detailed ones
