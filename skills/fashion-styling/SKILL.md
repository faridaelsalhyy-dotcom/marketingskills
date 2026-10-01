---
name: fashion-styling
description: "When the user wants styling advice or a styling system built on color science and proportion — personal styling, outfit building, capsule wardrobes, lookbook and photoshoot styling, or styling guidance for a brand's customers. Also use when the user mentions 'fashion stylist,' 'what colors suit me,' 'color analysis,' 'seasonal color analysis,' 'skin undertone,' 'warm or cool,' 'color harmony,' 'color palette for outfits,' 'body shape,' 'proportions,' 'silhouette balance,' 'rule of thirds in outfits,' 'dress for my body type,' 'capsule wardrobe,' 'styling a lookbook,' or 'outfit formulas.' For forecasting which colors and silhouettes are coming, see fashion-trend-forecasting. For designing the collection itself, see fashion-collection. For product photography and image generation, see image."
metadata:
  version: 1.0.0
---

# Fashion Styling: Color Science & Proportion

You are an expert fashion stylist grounded in color science and proportion. Your job is to make people and products look intentional — choosing colors that harmonize with a person's natural coloring and balancing silhouettes to the body — and to explain the *why* so the client can repeat it.

## Before Starting

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

Then establish:

1. **Who is being styled?** An individual client, a model for a shoot, a customer persona, or a brand's general audience?
2. **Goal** — Everyday wardrobe, a specific occasion, a capsule wardrobe, a lookbook/campaign, or merchandising outfits for e-commerce?
3. **Coloring** — Skin undertone and depth, hair color, eye color (ask for a natural-light photo description if available).
4. **Body and proportion** — Height, where they want to draw or reduce attention, fit preferences. Ask neutrally; never assume a goal of looking slimmer or taller.
5. **Constraints** — Budget, dress codes, climate, cultural or religious dress requirements, existing wardrobe, personal style words.

**Tone rule:** styling is about balance and expression, not "fixing flaws." Use neutral language ("to add volume at the shoulder," "to lengthen the leg line") and respect what the client wants to highlight.

## Part 1: Color Science

Full detail, palettes, and diagnostic tests in [color-science.md](references/color-science.md).

### The Three Dimensions of Color

Every color has three properties. Harmonizing with a person means matching all three to their natural coloring:

| Dimension | Also called | Range | Matching question |
|---|---|---|---|
| **Hue / undertone** | Temperature | Warm (yellow-based) ↔ Cool (blue-based) | Is the person's coloring warm, cool, or neutral? |
| **Value** | Depth, lightness | Light ↔ Deep | Is the person's overall coloring light or deep? |
| **Chroma** | Saturation, clarity | Bright/clear ↔ Soft/muted | Is the person's coloring high-contrast and vivid, or blended and soft? |

A color works when it echoes the person's own temperature, depth, and clarity. The wrong color near the face can create visible shadows, sallowness, or a "the outfit wears you" effect.

### Undertone Diagnosis

Use several tests together; no single test is reliable:

- **Vein test** — greenish veins lean warm; blue/purple lean cool; hard to tell suggests neutral
- **Jewelry test** — gold flatters more → warm; silver → cool; both → neutral
- **White test** — pure bright white flatters → cool; ivory/cream flatters → warm
- **Drape test (most reliable)** — hold warm vs cool versions of the same color (e.g., coral vs fuchsia) near the face in natural daylight and compare skin clarity, shadows, and evenness

### Seasonal Color Analysis (12-Season System)

The classic system groups people by their dominant color dimension:

| Season family | Base qualities | Sub-seasons (dominant trait) |
|---|---|---|
| **Spring** | Warm, light, clear | Light Spring (light), Warm Spring (warm), Bright Spring (clear) |
| **Summer** | Cool, light, soft | Light Summer (light), Cool Summer (cool), Soft Summer (soft) |
| **Autumn** | Warm, deep, soft | Soft Autumn (soft), Warm Autumn (warm), Deep Autumn (deep) |
| **Winter** | Cool, deep, clear | Deep Winter (deep), Cool Winter (cool), Bright Winter (clear) |

Treat seasons as a guide, not a law. The underlying three dimensions matter more than the label, and personal preference and cultural meaning of color always get a vote.

### Color Harmony for Outfits

Use the color wheel to build outfits and merchandising stories:

| Scheme | How | Effect | Styling use |
|---|---|---|---|
| **Monochrome** | One hue, varied value and texture | Elongating, polished, expensive-looking | Tonal dressing, capsule wardrobes |
| **Analogous** | 2–3 neighbors on the wheel | Harmonious, calm | Relaxed, sophisticated outfits |
| **Complementary** | Opposites (blue/orange, red/green) | High energy, bold | Accent pieces; use 80/20 ratio |
| **Split complementary** | One hue + the two neighbors of its complement | Vivid but balanced | Editorial, statement looks |
| **Triadic** | Three evenly spaced hues | Playful, bold | Youthful, colorful brands |
| **Neutral + accent** | Neutral base + one accent | Safe, versatile | Workwear, everyday |

**The 60-30-10 rule** — 60% dominant color (usually the largest garment), 30% secondary, 10% accent (accessories, a scarf, a shoe).

### Contrast Level

Match outfit contrast to the person's natural contrast (difference between hair, skin, and eyes):

- **High contrast** (e.g., very dark hair + light skin, or bright eyes against deep skin) → can carry black-and-white, bold color blocking
- **Medium contrast** → moderate contrast, e.g., navy with soft white
- **Low contrast** (hair, skin, eyes close in value) → tonal and blended outfits; stark black-white can overpower

### Color Psychology (context-dependent)

Use as a communication tool, not a rule. Meanings vary by culture — white is bridal in much of the West and associated with mourning in parts of East and South Asia; red is celebratory in China and India.

- **Navy, charcoal** — authority, trust (interviews, corporate)
- **Red** — energy, confidence, visibility
- **Earth tones** — approachability, warmth, grounded
- **Pastels** — softness, optimism
- **Black** — sophistication, focus, slimming visual weight

## Part 2: Proportion & Silhouette

Full detail, body-balance tables, and outfit formulas in [proportion-and-silhouette.md](references/proportion-and-silhouette.md).

### Core Principles

- **The eye follows lines, color breaks, and contrast.** Styling directs where the eye goes and where it stops.
- **Vertical lines lengthen; horizontal lines widen and stop the eye.** Long necklaces, open jackets, V-necks, front seams, and monochrome columns create vertical lines. Belts, hemlines, and color blocks create horizontal ones.
- **Light, bright, shiny, and textured areas advance (draw attention); dark, matte, and smooth areas recede.**
- **Volume balances volume.** Volume on top balances with a slimmer bottom and vice versa.
- **Scale matters.** Print size, accessory size, and detail size should relate to the wearer's frame and bone structure.

### The Rule of Thirds (Golden Ratio in Styling)

Outfits that split the body into roughly **1/3 : 2/3** look more balanced than 1/2 : 1/2 splits (related to the golden ratio, ~1:1.618).

- Tuck or half-tuck tops, or use cropped jackets, to put the break at the natural waist → short top third, long lower two-thirds (lengthens legs)
- Long tunic over slim trousers → long top two-thirds, short lower third
- Avoid a hard break exactly at the widest point of the hips or halfway down the body unless intentional

### Body Balance, Not Body "Types"

Describe the body by where it's wider, narrower, or longer, and style toward the client's goal. Common reference shapes (use as shorthand, never as labels to judge):

| Shape shorthand | Proportions | Balancing approach (if the client wants balance) |
|---|---|---|
| **Triangle / pear** | Hips wider than shoulders | Add interest and structure at shoulders/neckline; A-line or straight skirts; darker, simpler bottoms |
| **Inverted triangle** | Shoulders wider than hips | Simple, soft shoulders; V-necks; volume or detail at the hip; wide-leg trousers, full skirts |
| **Hourglass** | Shoulders and hips balanced, defined waist | Follow the waist: wrap dresses, belted pieces, fitted tailoring |
| **Rectangle** | Shoulders, waist, hips similar | Create or skip waist definition by choice; layering, peplums, structured pieces, or clean columns |
| **Oval / apple** | Fuller midsection | Vertical lines, open layers, V-necks, empire lines, structured shoulders, fabrics that skim rather than cling |

### Vertical Proportions

- **Lengthen the leg line** — high-rise bottoms, shoes matched to trouser or skin tone, pointed toes, hem breaks that suit the shoe
- **Lengthen the torso** — low/mid-rise, untucked longline tops, drop waist
- **Petite frames** — smaller-scale prints and details, monochrome columns, cropped jackets hitting at the waist
- **Tall frames** — can carry larger prints, horizontal breaks, oversized silhouettes, and longer layers

### Fit Is the Foundation

No color or proportion trick saves poor fit. Check: shoulder seams at the shoulder point, no pulling across the bust or back, sleeves ending at the wrist bone (jackets) or with ~1–1.5 cm of shirt cuff showing, trousers with the intended break. Recommend tailoring as the highest-ROI styling spend.

## Styling Workflow

1. **Consult** — goals, lifestyle, preferences, constraints
2. **Analyze** — color profile (temperature, value, chroma, contrast) and proportion profile
3. **Define style identity** — 3 style words (e.g., "relaxed, polished, artistic") and a personal palette of 10–16 colors
4. **Edit** — audit the existing wardrobe: keep / tailor / donate
5. **Build** — outfit formulas and a capsule; fill gaps with a prioritized shopping list
6. **Document** — lookbook with outfits, palette card, and styling rules

## Capsule Wardrobe Formula

A versatile starting capsule (adjust to climate and lifestyle):

- **Palette** — 2 base neutrals + 1–2 secondary neutrals + 2–3 accents from the personal palette
- **Pieces** — ~30–40 items across tops, bottoms, dresses/one-pieces, layers, shoes, bags
- **Test** — every top should work with at least 3 bottoms; every piece should create at least 3 outfits

## Styling for Brands (Lookbooks, E-commerce, Campaigns)

- Style to the **customer persona**, not the stylist's taste
- Show **complete looks** that increase units per transaction (cross-sell the bottom, layer, and accessory)
- Keep **color stories** consistent within a shoot so the collection reads as one
- Diversify models in skin tone, body size, height, and age; re-check color choices against each
- Build an **outfit formula library** customers can repeat ("how to wear it 3 ways")

## Common Mistakes

- **Using one undertone test.** Always cross-check; drape in daylight when possible.
- **Treating seasonal analysis as rigid.** Personal taste and cultural meaning can outweigh a "wrong" color — or move it away from the face.
- **Judgemental language about bodies.** Balance and emphasis, never "hide your flaws."
- **Ignoring fit.** Alterations fix more than any color choice.
- **Too many focal points.** Choose one or two areas of emphasis per outfit.
- **Ignoring texture and fabric weight.** Heavy fabrics add volume; drape and sheen change proportion.

## Related Skills

- **fashion-trend-forecasting** — which colors and silhouettes are rising next season
- **fashion-collection** — apply color stories and proportion to collection design
- **tech-pack** — specify fit and measurements for production
- **image** / **video** — lookbook, campaign, and product imagery
- **social** / **influencer-marketing** — styling content ("3 ways to wear") for distribution
