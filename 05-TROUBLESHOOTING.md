# 05 — Troubleshooting

## Common Failures & Fixes

These are real issues encountered during production. Every fix here was learned from an actual failed generation.

---

### Problem: Skin looks waxy / airbrushed
**Cause:** Model defaulting to beauty mode
**Fix:** Add explicit skin texture to prompt:
```
"visible pores on nose and cheeks, natural skin texture with slight unevenness in tone, minor blemish near [location], real skin not retouched"
```
Also add to negative: `no smooth skin, no porcelain skin, no beauty mode, no facetune`

---

### Problem: Ring light circles in eyes
**Cause:** Model defaulting to studio/influencer lighting
**Fix:** Be very specific about light source:
```
"soft natural window light from the left, irregular window-shaped catchlight in eyes"
```
Add to negative: `no ring light, no ring light catch lights, no circular catchlights, no studio lighting`

---

### Problem: Perfect symmetrical face
**Cause:** Model optimizing for "attractive"
**Fix:** Add asymmetry cues:
```
"natural facial asymmetry, one side of smile slightly higher, one eyebrow barely more arched than the other"
```
Don't mention symmetry at all (even saying "no symmetry" can backfire)

---

### Problem: Portrait mode blur in background
**Cause:** Model associating "selfie" with portrait mode
**Fix:** Be emphatic about depth of field:
```
"deep depth of field with everything in sharp focus including background, NO blur, NO bokeh, NOT portrait mode, standard iPhone camera mode"
```

---

### Problem: Expression too dramatic / theatrical
**Cause:** Expression descriptions are amplified by the model
**Fix:** The 30% rule. Whatever you want, describe it at a third:
- Want a smile → "lips barely curved upward, warmth mostly in the eyes"
- Want surprise → "one eyebrow slightly raised, mouth relaxed"
- Want sadness → "slightly downturned gaze, jaw slightly tight"

Describe the **physical movement**, not the emotion. "Lips 3mm apart" > "surprised expression"

---

### Problem: Hands or phone appearing in frame
**Cause:** Model associating "selfie" with visible phone
**Fix:** Crop tighter and be explicit:
```
"shot from mid-chest up, NO hands visible, NO phone in frame, NO mirror selfie"
```

---

### Problem: Person looks like a stock photo model
**Cause:** Too many positive descriptors, not enough "real" anchors
**Fix:** Add imperfection anchors:
```
"slight under-eye warmth, natural laugh lines, hair not perfectly styled, one shoulder slightly higher than the other, clothing with visible wrinkles"
```
The more specific imperfections you describe, the more real the output looks

---

### Problem: Background too clean / staged
**Cause:** Model creating "ideal" environments
**Fix:** Add lived-in details:
```
"simple kitchen background with a coffee mug and mail on the counter, slightly cluttered but not messy, real lived-in home"
```

---

### Problem: Content policy blocks the generation
**Cause:** Medical/health language triggering safety filters
**Fix:** Describe appearance, not function:
- ❌ "woman taking a supplement" → ✅ "woman holding a small bottle"
- ❌ "health product" → ✅ "matte pouch with green label"
- ❌ "experiencing bloating" → ✅ "frustrated expression"
See the ad factory compliance rules for full list of replacements

---

### Problem: Same person keeps getting generated
**Cause:** Not enough demographic variation in prompts
**Fix:** Be very specific and different in the person description:
- Change age by at least 5 years
- Different hair type/length/color
- Different skin tone
- Different build
- Different clothing style entirely

---

## The Nuclear Option

If a prompt keeps failing despite fixes:
1. Start completely fresh — don't iterate on a broken prompt
2. Write the new prompt by describing a REAL person you know (then change identifying details)
3. Keep it shorter — long prompts give models more to get wrong
4. Focus on the 80/20: skin texture, natural light, off-center gaze, deep DOF, worn clothes
