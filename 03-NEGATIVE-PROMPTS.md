# 03 — Negative Prompt Library

## Why Negatives Matter

Image gen models default to "pretty." Left unchecked, they'll add studio lighting, smooth skin, perfect symmetry, and portrait blur. Negative prompts are your guardrails against AI-looking output.

**Include the master negative on EVERY generation.** Add category-specific negatives as needed.

## Master Negative (Always Include)

```
No bokeh, no portrait mode, no shallow depth of field, no gaussian blur, no DSLR quality, no studio lighting, no ring light, no ring light catch lights, no softbox, no beauty dish, no three-point lighting, no perfect skin, no porcelain skin, no airbrushed skin, no smooth skin filter, no beauty mode, no facetune, no pore removal, no perfectly centered, no symmetrical face, no model pose, no stock photo, no editorial, no phone visible in frame, no mirror selfie, no hands in frame, no exaggerated expression, no theatrical expression, no wide open mouth.
```

## Category-Specific Additions

### For Women
```
No heavy makeup, no false eyelashes, no lip filler look, no contour makeup, no highlighted cheekbones, no beauty influencer aesthetic, no salon hair.
```

### For Men
```
No perfectly groomed beard, no model jawline emphasis, no fitness model posing, no flex pose, no gym mirror selfie.
```

### For Outdoor Shots
```
No golden hour glow filter, no lens flare, no HDR effect, no saturated colors, no landscape photography quality.
```

### For Kitchen/Home Settings
```
No interior design magazine, no staged kitchen, no perfectly clean counter, no showroom, no minimalist aesthetic.
```

### For Gym/Athletic Shots
```
No fitness magazine pose, no professional sports photography, no dramatic lighting, no pump pose, no flexing.
```

## Emergency Negatives

When a generation comes back looking AI despite your best prompt, add these aggressively:

```
NOT ai generated, NOT computer generated, NOT digital art, NOT 3D render, NOT illustration, NOT concept art, NOT photoshop, NOT retouched, NOT enhanced, NOT filtered, NOT beauty app, NOT smooth, NOT perfect, NOT flawless, NOT pristine, NOT immaculate.
```

## Pro Tip: Diagnose Before Adding

When a result looks off, identify the SPECIFIC AI tell before throwing negatives at it:
- Skin too smooth → add skin-specific negatives
- Eyes too perfect → add "no symmetrical eyes, no perfect catchlights"
- Hair too styled → add "no salon-styled hair, no perfectly placed strands"
- Background too clean → add "no staged background, no interior design"

Targeted negatives > shotgun approach.
