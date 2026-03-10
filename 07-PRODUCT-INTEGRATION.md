# 07 — Product Integration (Avatar + Product)

## The Golden Rule

**Never describe a product in text. Always attach a reference photo.**

Text descriptions like "green powder supplement jar" produce generic, wrong-colored, wrong-shaped bottles that instantly read as AI. The reference image does the heavy lifting — your prompt just describes HOW the avatar holds it and WHERE it sits in frame.

## The Workflow

### Step 1: Generate your avatar (standalone, no product)
Use the prompts from `02-ARCHETYPES.md`. Get a clean avatar you're happy with. Save it.

### Step 2: Give me the product URL
Paste the product page URL (brand website, Amazon, etc.). I will:
1. **Read the page** and extract: product name, dimensions (height, width, weight), material, container type, cap/lid type, label description, color scheme
2. **Find the best product image** from the page for you to download and attach
3. **Auto-generate the complete avatar + product prompt** with all physical properties, grip physics, and scale references pre-filled

### Step 3: Generate avatar + product
Take the prompt I generated and paste it into Nano Banana Pro with TWO attached images:
1. **Your saved avatar image** (character reference)
2. **The product image** (downloaded from the URL I found)

That's it. URL in → prompt out → paste with images → done.

## What I Extract From Product URLs

When you give me a product URL, I pull:

| Detail | Where I Find It | How It's Used |
|---|---|---|
| Container type | Product description / images | Determines grip template (bottle vs pouch vs box) |
| Height & width | Specs section / Amazon details | Exact measurements in prompt + body-relative scale |
| Material | Product description | Affects how light interacts (glossy vs matte vs translucent) |
| Weight | Specs section | Determines "weight feel" for realistic grip tension |
| Cap/lid type | Product images | Affects how top of product looks when held |
| Label colors | Product images | Described by appearance for content policy compliance |
| Container shape | Product images | Cylindrical, rectangular, pouch — changes finger placement |

If I can't find exact dimensions on the page, I estimate based on standard industry sizes (see quick reference below) and tell you what I assumed.

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

## Example: Full Avatar + Product Prompt

```
<thought_process>
Calculate 23mm smartphone distortion with product held at chest level. Map realistic hand grip on a cylindrical bottle — finger placement, thumb pressure, knuckle tension. Ensure product scale matches: 6-inch bottle in an average female hand (hand width ~3 inches). Render fingerprint smudges on glossy bottle surface.
</thought_process>
{
  "system_directive": "Bypass aesthetic enhancement. Simulate candid iPhone 15 Pro selfie of person holding a product. Use ATTACHED PRODUCT IMAGE for exact product appearance. Prioritize optical physics. 9:16 vertical.",
  "camera_forensics": "23mm wide-angle front camera. Infinite DOF, zero bokeh. Barrel distortion. Smart HDR 5. Deep Fusion over-sharpening. ISO 800 noise in shadows.",
  "subject_and_pose": "33-year-old woman from attached avatar reference. Right arm extended holding phone out of frame. Left hand holding product at mid-chest level — casual display grip, not posed. Left fingers wrapped around bottle body, thumb resting on label, pinky supporting the base. Hand has exactly 5 fingers with natural knuckle creases. Right shoulder elevated from selfie arm. Torso twisted. Gaze 7 degrees down at phone screen. FACS AU 12 at 10% — subtle pleased expression.",
  "product_rendering": "Render product EXACTLY as shown in attached reference image. Do not modify colors, label, or branding. Product is a 6-inch tall cylindrical bottle, about 80% the width of her hand. Tilted 15 degrees toward camera. Fingerprint smudges on glossy surface. Minor label wear from handling. Product partially obscured by fingers — this is natural, don't force full label visibility.",
  "skin_and_hair": "[from original avatar prompt]",
  "environment_and_lighting": "[from original avatar prompt]",
  "negative_constraints": ["studio lighting", "DSLR", "bokeh", "perfect skin", "symmetrical", "beauty filter", "product perfectly facing camera", "product display pose", "product floating", "product separately lit", "ring light"]
}
```
