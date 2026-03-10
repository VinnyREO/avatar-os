# 04 — Negative Prompts (Nano Banana Pro)

## How Negatives Work in Nano Banana Pro

Nano Banana Pro processes negatives through **semantic exclusion**, not weightings (`::-1`). This means:
- Keyword salads like "ugly, extra fingers, bad anatomy" are **placebos**
- Semantic concepts like "studio photography aesthetics" actually work
- The model understands intent — describe what to EXCLUDE conceptually

## Master Negative Block (Always Include)

Copy this into every prompt:

```json
"negative_constraints": [
  "studio photography aesthetics",
  "three-point lighting",
  "rim lighting",
  "mathematical facial symmetry",
  "professional color grading",
  "bokeh depth of field",
  "blurred background",
  "DSLR 85mm lens compression",
  "airbrushed high-end beauty retouching",
  "beauty filters",
  "stock photo posture"
]
```

## Situation-Specific Additions

### For Women (add to master)
```json
"heavy cosmetic makeup",
"false eyelash rendering",
"beauty influencer aesthetic",
"salon-styled hair",
"contoured facial makeup"
```

### For Men (add to master)
```json
"perfectly groomed facial hair",
"fitness model posing",
"GQ editorial aesthetic",
"muscle definition emphasis"
```

### For Outdoor Shots (add to master)
```json
"golden hour glow filter",
"lens flare",
"HDR tone mapping effect",
"oversaturated nature colors",
"landscape photography composition"
```

### For Kitchen/Home (add to master)
```json
"interior design magazine aesthetic",
"staged minimalist decor",
"perfectly clean surfaces",
"showroom lighting"
```

### For Post-Workout (add to master)
```json
"fitness magazine composition",
"professional sports photography lighting",
"dramatic athletic pose",
"hero shot framing"
```

## What DOESN'T Work (Don't Waste Tokens)

These are placebos in Nano Banana Pro — the model ignores them:
- "ugly" / "deformed" / "bad anatomy"
- "extra fingers" / "extra limbs"
- "watermark" / "text"
- "low quality" / "blurry"
- "cartoon" / "anime"

These worked in Stable Diffusion/Midjourney but Nano Banana Pro's LLM reasoning engine doesn't process them meaningfully.

## Emergency Fix

When output still looks AI despite negatives:

```json
"negative_constraints": [
  "ALL studio photography conventions",
  "ALL professional lighting setups",
  "ALL beauty and skin retouching",
  "ALL symmetry optimization",
  "ALL professional composition rules",
  "Render as raw unprocessed smartphone sensor data"
]
```
