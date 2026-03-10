# 08 — Variation Mode (Rapid Avatar Swapping)

## The Concept

Once you have ONE good image of a person holding the product correctly, use it as a seed to generate unlimited variations — different people, different settings, same product. Nano Banana Pro generates 4 images at once, so every prompt = 4 new avatars.

## The Workflow

### Step 1: Get your first good image
Generate (or find) one image where the product looks right — correct size, correct grip, natural UGC style. This is your **seed image**.

### Step 2: Attach the seed image + short variation prompt
Keep it vague. Don't over-specify. Let the model generate variety on its own.

### Step 3: Repeat
Each run = 4 new avatars. Run it 5 times = 20 avatars. Cherry-pick the best.

## The Proven Prompt Template

Attach your seed image and use this:

```
Change the avatar. Change the situation fitting for this "[product type]". Same raw style as reference image. Different person, new situation, same product. [gender] [age range] avatar.
```

### Real Example (Tested & Working):
```
Change the avatar. Change the situation fitting for this "bath soaks product". Same raw style as reference image. Different person, new situation, same product. Female 20-35 avatar.
```

**That's it.** Short, vague, effective. The seed image does the heavy lifting — the model copies the product, the style, and the framing while swapping the person and setting.

## Why Short Prompts Work Better

- Long detailed prompts make the model focus on the wrong things (product specs → product photography mode)
- "Same raw style as reference image" locks the UGC feel without over-engineering
- "Change the situation fitting for this [product]" lets the model pick contextually appropriate settings
- The model generates more natural variety when it has creative freedom

## Variations You Can Run

**Different demographics:**
```
Change the avatar. Same product, same raw style. Male 30-45 avatar. New fitting situation.
```

**Different age range:**
```
Change the avatar. Same product, same raw style. Female 40-55 avatar. New fitting situation.
```

**Multiple at once (batch diversity):**
```
Change the avatar. Same product, same raw style. Each avatar should be a completely different person — different age, ethnicity, and setting. Mix of genders.
```

**Specific setting:**
```
Change the avatar. Same product, same raw style. Female 25-35 avatar. Morning kitchen setting.
```

**Keep it loose for maximum variety:**
```
New avatar. Same product. Same style. Surprise me.
```

## Tips

- **Save your best seed image** for each product — it's your master reference
- **If the product drifts** (colors change, wrong shape), go back to the original seed
- **Cherry-pick aggressively** — out of every 4 generations, usually 1-2 are great, 1 is usable, 1 is off
- **The shorter the prompt, the more natural the output** — resist the urge to add details
- **Run the same prompt multiple times** — you'll get different results each time
- **"Same raw style"** is the magic phrase — it anchors the UGC selfie aesthetic from your seed
