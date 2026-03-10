# 06 — Troubleshooting (Nano Banana Pro)

## Problem → Diagnosis → Fix

---

### Skin looks waxy / airbrushed
**Cause:** Nano Banana Pro's "Google Glow" perfection bias
**Fix:** Use clinical dermatological terms:
```json
"skin_and_hair": "Heterogeneous pore distribution: stretched sebaceous pores on nasal ala. Fine vellus hair catching light on jawline. Suborbital venous pooling. Natural sebum shine on T-zone only. Variable subsurface scattering: translucent ear tips, opaque forehead."
```

---

### Ring light catchlights in eyes
**Cause:** Model defaulting to influencer aesthetic
**Fix:** Explicitly specify phone screen catchlight:
```json
"Rectangular smartphone screen catchlight in both eyes, positioned in upper third of iris. No circular catchlights."
```

---

### Face looks like DSLR portrait (too compressed, blurry background)
**Cause:** Model defaulting to 85mm full-frame aesthetic
**Fix:** Hammer the iPhone specs:
```json
"camera_forensics": "23mm wide-angle front camera barrel distortion at 18-inch distance. Infinite depth of field — background PERFECTLY SHARP, zero bokeh, zero blur. This is a smartphone, not a DSLR."
```

---

### Expression too dramatic
**Cause:** Model amplifying emotion descriptors
**Fix:** Use FACS units with low percentages:
- Want smile → "FACS AU 12 at 8-10%"
- Want surprise → "FACS AU 1+2 at 10-15%"
- Want neutral → "Natural resting muscle tone, asymmetric lip line"

Never write "happy," "excited," "surprised" as standalone descriptors.

---

### Looks like a stock photo model
**Cause:** Too many positive descriptors, not enough imperfection anchors
**Fix:** Add specific imperfections:
```json
"Anatomical facial asymmetry: left eye 2mm lower, nasal septum deviated 3 degrees. One eyebrow slightly more arched. Healing blemish near jawline. Asymmetric lip line."
```

---

### Background too clean / staged
**Cause:** Model creating "ideal" environments
**Fix:** Force clutter and amateur composition:
```json
"environment": "Slightly off-center amateur composition, top of head slightly cropped out. Background: fully in-focus cluttered kitchen counter — half-empty water glass, crumpled paper towel, open cabinet door, a few pieces of mail."
```

---

### Content policy blocks the generation
**Cause:** Medical/health language triggering filters
**Fix:** Describe appearance, not function:
- ❌ "holding a supplement" → ✅ "holding a matte pouch with green label"
- ❌ "health product" → ✅ "small branded bottle with white cap"
- ❌ "experiencing bloating" → ✅ "frustrated expression, FACS AU 4 at 15%"

---

### Same person keeps generating
**Cause:** Not enough demographic variation
**Fix:** Change multiple variables simultaneously:
- Different age by 5+ years
- Different hair type/length/color
- Different skin tone and undertone
- Different build
- Different clothing style entirely
- Different lighting scenario

---

### Clothing looks painted on
**Cause:** Model ignoring fabric physics
**Fix:** Specify tension, gravity, and wear:
```json
"Wearing a washed cotton hoodie with diagonal tension folds pulling toward elevated right shoulder. Visible double-stitched hem, realistic fabric thickness at collar. Natural memory wrinkles at inner elbows. Pilling at cuffs, subtle fade on shoulder seams."
```

---

### Shoulders are perfectly level / posture too perfect
**Cause:** Model ignoring selfie arm biomechanics
**Fix:** Always include the biomechanics block:
```json
"subject_and_pose": "Right arm extended holding phone out of frame. Right shoulder distinctly elevated and rotated inward. Torso twisted 15 degrees off-axis to the left. Cervical spine tilts 5 degrees right to compensate. Sternocleidomastoid neck tendon visibly tense on one side."
```

---

## Nuclear Option

If prompt keeps failing:
1. Start completely fresh — don't iterate on broken prompts
2. Use the Master Prompt template from SYSTEM-PROMPT.md
3. Only change: person description, lighting scenario, and environment
4. Keep everything else exactly as the template specifies
5. If still failing, simplify — shorter prompts give the model less to get wrong
