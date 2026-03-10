# 07 — Product Integration (Avatar + Product)

## The Workflow

**One step. One image. One prompt.**

You give me:
1. A **product URL** (brand website or Amazon)
2. What kind of **person** you want (age, gender, vibe — or just the product category and I'll pick the right archetype)

I give you:
1. A **complete prompt** with the avatar AND product combined — ready to paste
2. Which **product image** to download and attach

You paste the prompt into Nano Banana Pro with the product image attached → get a realistic person holding the real product.

**That's it.** No 2-step process. No separate avatar generation. One shot.

## What I Extract From Product URLs

When you give me a product URL, I read the page and pull:

| Detail | How It's Used in the Prompt |
|---|---|
| Container type (bottle/pouch/box) | Determines grip template — which fingers go where |
| Height & width | Exact measurements + body-relative scale ("80% of hand width") |
| Material (plastic/glass/matte/glossy) | How light interacts with the surface, fingerprint visibility |
| Weight | Grip tension — light products held loosely, heavy ones gripped firmly |
| Cap/lid type | What peeks above the fingers when held |
| Label colors & design | Described by appearance only (content policy safe) |
| Container shape | Cylindrical vs rectangular vs flexible — changes hand wrap |

If dimensions aren't on the page, I estimate from industry standard sizes (see table below) and note my assumption.

## The Golden Rules

1. **Product image does the heavy lifting.** The attached reference photo shows what the product looks like. The text prompt describes HOW it's held and HOW BIG it is. Never describe the product's appearance in text — always reference the attached image.

2. **"Render the product EXACTLY as shown in the attached reference image. Do not modify, redesign, or reinterpret any aspect of the product — preserve exact colors, label, branding, shape, cap, and finish."** ← This line goes in every prompt.

3. **Describe by appearance, not function.** Content policy blocks health language.
   - ❌ "supplement bottle" → ✅ "matte green cylindrical container with white screw cap"
   - ❌ "protein powder" → ✅ "large flexible pouch with colorful label"

4. **Specify 5 fingers.** AI hands need this explicitly.

5. **Add handling marks.** Fingerprint smudges, slight powder residue, minor label wear = realism.

## Product Physics Block

The model needs to know the product's physical properties to render it correctly. Include this in your prompt:

```json
"product_integration": {
  "reference": "USE ATTACHED PRODUCT IMAGE for exact appearance, colors, label, branding. Do not invent or modify any product details.",
  "physical_properties": {
    "type": "[bottle/pouch/box/jar/tube/packet]",
    "height": "[X inches/cm]",
    "width": "[X inches/cm]",
    "material": "[plastic/glass/matte pouch/rigid box/foil packet]",
    "weight_feel": "[light like empty water bottle / medium like full water bottle / heavy like glass jar]"
  },
  "grip_and_placement": {
    "held_how": "[casual one-hand grip near bottom / cradled in palm / pinched at top / resting on counter in front of them / tucked under arm]",
    "hand_position": "[describe which fingers wrap where — e.g., 'thumb on front label, four fingers wrapped around back, pinky near base']",
    "product_angle": "[slightly tilted toward camera showing label / angled 20° away / straight on]",
    "scale_reference": "Product is [X]% the width of the subject's hand. [X] inches tall relative to their forearm length."
  }
}
```

## Common Product Types — Quick Reference

### Supplement Bottle (e.g., AG1, Seed, Ritual)
```json
"physical_properties": {
  "type": "cylindrical plastic or glass bottle",
  "height": "5-7 inches",
  "width": "2.5-3 inches diameter",
  "material": "opaque plastic with label wrap or glass with cap",
  "weight_feel": "medium, like a half-full water bottle"
},
"grip_and_placement": {
  "held_how": "Casual one-hand grip, relaxed fingers wrapped around middle of bottle",
  "hand_position": "Thumb resting on front label area, four fingers wrapped around back, bottom of bottle resting on edge of pinky",
  "product_angle": "Tilted 15 degrees toward camera, label partially visible",
  "scale_reference": "Bottle is about 80% the width of the subject's hand. Top of bottle reaches mid-forearm when held at waist level."
}
```

### Powder Pouch/Bag (e.g., AG1 travel packs, protein bags)
```json
"physical_properties": {
  "type": "flexible matte or metallic pouch",
  "height": "8-12 inches",
  "width": "5-7 inches",
  "material": "flexible foil-lined pouch, slightly crinkled, not rigid",
  "weight_feel": "light to medium, slightly floppy, conforms to hand shape"
},
"grip_and_placement": {
  "held_how": "Pinched at top with one hand, or cradled at bottom letting it drape",
  "hand_position": "Fingers pinching the top seal, pouch hanging naturally with gravity causing wrinkles and folds in the material",
  "product_angle": "Front label facing camera but with natural fold distortion",
  "scale_reference": "Pouch is about 1.5x the width of the hand. Hangs about 10 inches from grip point."
}
```

### Small Box (e.g., test kits, sample boxes)
```json
"physical_properties": {
  "type": "rigid cardboard box",
  "height": "4-6 inches",
  "width": "3-5 inches",
  "material": "matte or glossy rigid cardboard, sharp edges, printed graphics",
  "weight_feel": "light, like a deck of cards"
},
"grip_and_placement": {
  "held_how": "Held up near chest with one hand, fingers underneath supporting, thumb on top",
  "hand_position": "Four fingers curled under the bottom edge, thumb pressing on the top face, box slightly angled",
  "product_angle": "Angled 20 degrees showing front face and a sliver of the side",
  "scale_reference": "Box fits entirely within one hand. About the size of a smartphone."
}
```

### Gummies/Pill Bottle (e.g., Olly, SmartyPants)
```json
"physical_properties": {
  "type": "short wide plastic bottle with flip or screw cap",
  "height": "4-5 inches",
  "width": "2.5-3 inches diameter",
  "material": "translucent or opaque plastic, rounded shape",
  "weight_feel": "light, like a half-full pill bottle — slight rattle"
},
"grip_and_placement": {
  "held_how": "Casual palm grip, almost cupped in hand",
  "hand_position": "Fingers wrapped around the body, palm supporting the base, cap peeking above the index finger",
  "product_angle": "Straight on or slightly tilted, label facing camera",
  "scale_reference": "Bottle fits snugly in palm. Top of cap barely clears the top of a closed fist."
}
```

## Critical Rules

### 1. ALWAYS Attach the Product Photo
The reference image handles: exact colors, label design, branding, cap style, transparency, finish. Your text prompt handles: how it's held, where it is, how big it is relative to the person.

### 2. Describe Products by APPEARANCE, Not Function
Content policy will block health/medical language in image prompts:
- ❌ "supplement bottle" → ✅ "matte green bottle with white cap and label"
- ❌ "protein powder" → ✅ "large flexible pouch with colorful label"
- ❌ "test kit" → ✅ "small rigid box with navy branding"
- ❌ "health product" → ✅ "cylindrical bottle with printed wrap"

### 3. Specify 5 Fingers
AI hands fail without explicit instruction. Always include:
```
"Hand has exactly 5 fingers: thumb, index, middle, ring, pinky. Natural finger spacing, realistic knuckle creases, visible nail beds."
```

### 4. Product Scale Must Be Consistent
If someone's hand wraps around a bottle, the bottle can't be bigger than their forearm. Include real-world measurements and a scale reference to the person's hand/body.

### 5. Fingerprints and Smudges = Realism
Real products in real hands get dirty:
```
"Product surface shows fingerprint smudges, slight powder residue near the opening, minor label wear from daily handling."
```

### 6. Don't Obsess Over Logo Visibility
Real selfies often partially obscure the label. It's more authentic when:
- Fingers cover part of the logo
- The bottle is slightly angled away
- The label wraps around the curve and distorts

## Product Placement Positions (Natural UGC)

| Position | Best For | Prompt Language |
|---|---|---|
| Held near chest | "Just got this" reveal | "Product held at mid-chest level, close to body, casual display grip" |
| On counter in front | Morning routine | "Product sitting on counter surface in front of subject, slightly off-center in frame, subject behind it" |
| Mid-pour/scoop | Action shot | "Subject mid-action scooping from open container, spoon/scoop in one hand, jar in the other" |
| Tucked in hand, low | Casual mention | "Product held loosely at waist level in non-dominant hand, almost an afterthought in the frame" |
| Held up to camera | "Look at this" | "Product held up near face level, arm partially extended, showing label to camera" |

## Industry Standard Sizes (Fallback When Specs Unavailable)

| Product Type | Typical Height | Typical Width | Typical Weight | Examples |
|---|---|---|---|---|
| Capsule bottle (30-60ct) | 4-5" | 2-2.5" dia | 3-6 oz | Seed, Ritual, Athletic Greens capsules |
| Capsule bottle (90-120ct) | 5-6" | 2.5-3" dia | 6-10 oz | Garden of Life, NOW Foods |
| Powder canister (small) | 6-7" | 3.5-4" dia | 8-12 oz | AG1 canister, small protein |
| Powder canister (large) | 9-11" | 5-6" dia | 2-5 lbs | Protein powder tubs |
| Powder pouch/bag | 8-12" tall | 5-7" wide | 8 oz - 2 lbs | AG1 travel, protein bags |
| Gummy bottle | 4-5" | 2.5-3" dia | 4-8 oz | Olly, SmartyPants, Goli |
| Liquid dropper bottle | 4-5" | 1.5-2" dia | 1-2 oz | Tinctures, liquid vitamins |
| Single-serve packet | 5-6" tall | 3-4" wide | 0.5-1 oz | Stick packs, sachets |
| Rigid box (test kit) | 4-8" | 3-6" wide | 4-12 oz | Everlywell, at-home kits |
| Tube (cream/gel) | 5-7" | 1.5-2" dia | 2-4 oz | Topicals, gels |

## Example: One-Shot Avatar + Product Prompt

This is what a complete output looks like when someone says "I need avatars holding this product: [URL]":

```
<thought_process>
Calculate 23mm smartphone distortion with product held at chest level. Map realistic hand grip on a cylindrical bottle — finger placement, thumb pressure, knuckle tension. Ensure product scale: 7-inch canister in an average female hand (hand width ~3 inches, canister is ~130% of hand width). Render fingerprint smudges on matte surface. Mixed kitchen lighting with dual color temperature shadows on both skin and product surface.
</thought_process>
{
  "system_directive": "Bypass aesthetic enhancement. Simulate a casual, candid iPhone 15 Pro selfie. Render the product EXACTLY as shown in the attached reference image. Do not modify, redesign, or reinterpret any aspect of the product — preserve exact colors, label, branding, shape, cap, and finish. Prioritize optical physics and anatomical asymmetry. Output raw 9:16 vertical format.",
  "camera_forensics": "23mm equivalent wide-angle front camera. Infinite depth of field, background perfectly sharp, zero bokeh. Barrel distortion: enlarged nasal proportions, ears occluded by cheekbones. Apple Smart HDR 5 tone mapping, Deep Fusion micro-contrast over-sharpening on skin and product label texture. Mild ISO 800 noise in shadow gradients.",
  "subject_and_pose": "33-year-old Latina woman. Right arm extended holding phone out of frame. Right shoulder distinctly elevated and rotated inward. Torso twisted 15 degrees left. Left hand holding product at mid-chest level in a casual, relaxed grip — not presenting it to camera, just holding it naturally like mid-conversation. Left hand has exactly 5 fingers: thumb on front of container resting across label, four fingers wrapped around back with pinky near the base. Natural knuckle creases, visible nail beds, slight finger pad compression from grip pressure. Gaze directed 7 degrees downward at phone screen. FACS AU 12 at 10% — slight asymmetric lip corner pull, warmth in orbicularis oculi.",
  "product_rendering": "Product is a matte-finish cylindrical container, approximately 7 inches tall and 4 inches in diameter — about 130% the width of her hand. White screw cap visible above her index finger. Product tilted 15 degrees toward camera, label partially visible but naturally obscured by fingers. Fingerprint smudges on matte surface. Minor handling wear on label edge. Product catches the same mixed lighting as the subject — warm overhead light on cap, cool window light on the side facing camera. Do NOT separately light the product.",
  "skin_and_hair": "Day-two wavy dark hair with flyaways at temples, flattened roots at crown. Warm bronze skin with heterogeneous pore distribution: visible sebaceous pores on nose, smoother cheeks. Fine vellus hair catching light on jawline. Slight under-eye venous pooling. Natural sebum shine on T-zone. Subtle melasma near temples. Asymmetric eyebrow arch.",
  "environment_and_lighting": "Mixed kitchen lighting: warm tungsten overhead LEDs (3000K) casting downward shadows under brow, cool daylight (5500K) from side window. Dual color temperature on skin and product surface. Background: cluttered kitchen counter with open wooden shelving, half-empty water glass, crumpled paper towel. Everything in sharp focus. Rectangular phone screen catchlight in eyes.",
  "negative_constraints": ["studio lighting", "three-point lighting", "DSLR", "bokeh", "perfect skin", "mathematical facial symmetry", "beauty filter", "ring light", "airbrushed retouching", "product perfectly facing camera", "product display pose", "product floating", "product separately lit", "stock photo composition", "professional color grading"]
}
```

**User attaches:** The product image from the brand website
**Result:** Realistic person holding the exact product in a natural selfie
