# 01 — Photorealism Guide (Nano Banana Pro)

## The iPhone Selfie Standard

Every avatar must look like an iPhone 15 Pro front camera selfie taken by a real person at arm's length. Not a DSLR. Not a studio. Not portrait mode. A raw, computational-photography-processed smartphone capture.

## iPhone 15 Pro Front Camera — Exact Specs

These specs define every prompt you write:

| Spec | Value | Visual Impact |
|---|---|---|
| Sensor | 12MP, 1/3.6" | Tiny sensor = deep DOF, visible noise in shadows |
| Focal Length | 23mm equivalent | Wide-angle barrel distortion on faces |
| Aperture | f/1.9 | Combined with tiny sensor = near-infinite DOF |
| Processing | Smart HDR 5 + Deep Fusion | Lifted shadows, over-sharpened micro-contrast |
| Format | HEIC → JPEG | Compression artifacts visible on close inspection |
| Distance | 16-20 inches (arm's length) | Nose enlarged 10-15%, ears hidden behind cheekbones |

### Perspective Distortion at 23mm

This is the #1 thing AI gets wrong. A 23mm lens at arm's length creates **center-bulge barrel distortion**:
- Nose enlarges by 10-15%
- Forehead appears to slope backward
- Ears recede behind cheekbones (often invisible)
- Chin can appear slightly wider
- The eye closest to camera appears marginally larger

**Prompt language:** "23mm wide-angle front camera barrel distortion at 18-inch distance: enlarged nasal proportions, receding lateral jawline, ears entirely occluded by cheekbones, infinite depth of field."

### Apple's Computational Pipeline

Real iPhone photos have distinctive processing artifacts that AI never adds:
- **Smart HDR 5**: Flattens dynamic range, lifts shadows revealing chroma noise
- **Deep Fusion**: Aggressively over-sharpens micro-contrast (pores, eyelashes) while watercoloring low-light textures
- **Noise**: ISO 800+ luminance and chroma noise in shadow gradients
- **Compression**: HEIC to JPEG artifacts

**Prompt language:** "Apple Deep Fusion micro-contrast over-sharpening on skin textures. Smart HDR flattened highlights. HEIC to JPEG compression artifacts. Mild ISO 800 luminance and chroma noise in shadow gradients."

## Skin — The #1 AI Detector

Humans detect fake skin in under 0.5 seconds. Nano Banana Pro defaults to uniform "subsurface scattering" that looks like silicone.

### The 15 AI Skin Tells

| # | AI Default | Reality | Nano Banana Pro Fix |
|---|---|---|---|
| 1 | Uniform pore spacing | Real pores cluster irregularly | "Heterogeneous pore distribution: stretched sebaceous pores on nasal ala, transitioning to smooth lateral cheeks" |
| 2 | No peach fuzz | Everyone has vellus hair | "Fine vellus hair catching backlight on jawline, upper lip, and sideburn area" |
| 3 | Uniform skin color | Real skin has zones | "Distinct dermal color zones: periorbital darkness, perioral redness, T-zone sebum shine, malar flush" |
| 4 | Perfect under-eyes | Real under-eyes show veins | "Suborbital volumetric hollowing with translucent bluish venous pooling" |
| 5 | Smooth forehead | Real foreheads have texture | "Visible frontalis muscle texture, fine horizontal lines even at rest" |
| 6 | Even skin thickness | Varies across face | "Translucent thin skin at temples showing temporal veins, thicker sebaceous skin on nose" |
| 7 | No sebum | Real skin has oil | "Natural sebum shine concentrated on T-zone: forehead, nasal bridge, chin" |
| 8 | Perfect lip texture | Real lips have micro-texture | "Lip vermilion with vertical labial furrows, slight dryness at corners, uneven color saturation" |
| 9 | Uniform subsurface | Real SSS varies | "Variable subsurface scattering: translucent ear tips, opaque forehead, semi-translucent nasal ala" |
| 10 | No capillaries | Visible on thin skin | "Visible capillary network at nasal ala, inner cheeks, and temple area" |
| 11 | Symmetrical features | Real faces aren't | "Anatomical facial asymmetry: left eye 2mm lower, nasal septum deviated 3°, uneven lip line" |
| 12 | Porcelain neck | Necks have texture | "Platysmal bands visible on neck, horizontal necklace lines, texture change at jawline" |
| 13 | Perfect eyebrows | Real brows are uneven | "Asymmetric eyebrow arch, sparse areas at tail, individual hair direction variation" |
| 14 | Uniform cheek surface | Real cheeks vary | "Subtle acne scarring or texture variation on lateral cheeks, visible follicular openings" |
| 15 | Glowing skin | Real skin absorbs light | "Matte skin absorption with localized specular highlights only on sebaceous areas" |

### Skin by Ethnicity — Specific Adjustments

**Fair/Northern European:** "Translucent fair skin revealing subcutaneous vasculature, pink undertones in malar area, visible blue-green veins at temples, tendency toward erythema (redness) on cheeks and nose, sparse barely-visible blonde vellus hair."

**Mediterranean/Olive:** "Warm olive undertones with golden-yellow base pigmentation, slight hyperpigmentation around eyes, thicker dermal density with smaller pore visibility, natural protective melanin distribution."

**East Asian:** "Smooth dermal texture with smaller pore openings, warm yellow-beige undertones, minimal visible vasculature, characteristic flatter midface light distribution. Monolids or distinct epicanthic folds without exaggerated lifting, lower nasal bridge, wider bi-zygomatic width."

**South Asian/Brown:** "Rich warm brown undertones with significant melanin variation across face, periorbital hyperpigmentation, visible texture contrast between oily T-zone and matte cheeks, fuller lip pigmentation gradient."

**Black/African:** "Deep melanin with complex undertones (may be warm reddish, cool blue-black, or neutral). Authentic morphological features: broader alar base, full mucosal lips without artificial gloss, tight 4C coily hair with uneven shrinkage. Avoid Eurocentric skeletal defaults."

**Mixed-Race:** "Complex melanin distribution with visible heritage blending — specify the actual combination rather than defaulting to light brown homogeneity. Include feature variation that reflects real genetic mixing."

### Skin by Age

| Age | Key Markers |
|---|---|
| 25 | Smooth with minor textural variation, possible hormonal acne scarring, no expression lines at rest, full subcutaneous fat, even elasticity |
| 30 | First fine lines appear at lateral eye corners when smiling, early nasolabial fold, slight under-eye hollowing begins, pore size increasing on nose |
| 35 | Expression lines visible at rest around eyes, early forehead lines, periorbital volume loss, first grey hairs possible, skin texture becoming more heterogeneous |
| 40 | Established nasolabial folds, crow's feet at rest, forehead furrows, early jowling, neck texture changes, noticeable pore enlargement, uneven pigmentation |
| 45 | Deep expression lines, jawline softening, upper eyelid laxity, more pronounced pigmentation irregularity, lip volume decreasing, visible platysmal bands |
| 50 | Advanced volume loss in midface, deep marionette lines, textural roughening, significant sun damage visible, prominent neck lines, thinning eyebrows |
| 55 | Significant gravitational changes, heavy lid, deep furrows, mottled pigmentation, thin papery texture in areas, visible bone structure through volume loss |

## Eyes & Gaze

### Real vs AI Eyes

| Feature | AI Default | Reality |
|---|---|---|
| Catchlights | Circular (ring light) | Rectangular (phone screen) |
| Gaze | Dead-center at lens | 7° downward at phone screen |
| Iris | Perfectly round, vivid color | Irregular pupil border, muted natural color |
| Sclera | Pure white | Slight yellow/blue tint, visible blood vessels |
| Moisture | Uniform shine | Tear film meniscus at lower lid margin |
| Symmetry | Both eyes identical | One eye slightly more open, different angle |

**Prompt language:** "Rectangular smartphone screen catchlight in both eyes. Gaze directed 7 degrees downward at phone screen, not at camera lens. Natural iris with irregular pupil border. Sclera with faint blood vessels. Slight tear film meniscus at lower lid."

## Hair — Day State Matters

Always specify the hair's current state, not its ideal form:

| State | Visual Characteristics |
|---|---|
| Day 1 (fresh) | Volume, bounce, individual strand separation, slight frizz from drying method |
| Day 2 | Flattened roots, oil at crown, texture more clumped, flyaways at temples |
| Day 3 | Visible grease at part line, clumped texture, pulled back is more likely |
| Post-workout | Damp at temples and nape, frizzy halo, pieces stuck to neck/face |
| Hat hair | Flattened crown, indentation line, frizzy below the line |

**Prompt language (Day 2):** "Day-two wavy hair with flattened oily roots at the crown, static flyaways at temples, clumped texture through mid-lengths, slight frizz halo, natural part slightly greasy."

## Clothing — Fabric Physics

AI renders clothing as if it's painted on. Real fabric has:
- **Gravity**: Pulls downward, creates diagonal tension folds toward anchor points
- **Memory wrinkles**: At elbows, armpits, wherever fabric is repeatedly folded
- **Wear patterns**: Fading at collar, pilling at cuffs, stretched neckline
- **Thickness**: Visible at seams, hems, collar construction

**Prompt language:** "Wearing a washed, slightly pilled grey cotton hoodie with diagonal tension folds pulling toward the elevated right shoulder. Visible double-stitched hem, realistic fabric thickness at the collar, natural memory wrinkles at inner elbows. Subtle fade on high-friction shoulder seams."

## Selfie Arm Biomechanics

The selfie arm creates a cascade of body adjustments AI ignores:

**Prompt language:** "Simulate one-handed selfie musculoskeletal posture: Right arm extended out of frame. Right shoulder distinctly elevated and rotated inward. Torso twisted 15 degrees off-axis to the left. Cervical spine tilts 5 degrees right to compensate. Sternocleidomastoid neck tendon visibly tense on one side. Slight slump in non-dominant shoulder."
