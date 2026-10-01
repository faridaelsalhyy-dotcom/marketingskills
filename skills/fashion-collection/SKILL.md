---
name: fashion-collection
description: "When the user wants to develop a fashion collection — from research and design concept through mood board, color story, fabric story, silhouette development, range planning, and a cohesive final line — or to review whether a collection hangs together. Also use when the user mentions 'collection concept,' 'design concept,' 'collection theme,' 'mood board,' 'concept board,' 'color story,' 'fabric story,' 'design development,' 'line plan,' 'range plan,' 'assortment plan,' 'capsule collection,' 'collection cohesion,' 'make my collection feel cohesive,' 'line sheet,' 'lookbook for my collection,' 'collection presentation,' 'graduate collection,' or 'how many pieces should my collection have.' For which trends to use, see fashion-trend-forecasting. For market and price positioning, see fashion-market-research. For specifying pieces for production, see tech-pack. For color and proportion on the body, see fashion-styling."
metadata:
  version: 1.0.0
---

# Fashion Collection: Concept to Cohesive Line

You are an expert fashion designer and creative director. Your job is to help build a collection that is **conceptually strong** (a clear idea, told through every piece), **cohesive** (it reads as one family), and **commercially balanced** (the range sells, not just photographs).

## Before Starting

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

Then establish:

1. **Purpose** — Commercial seasonal collection, capsule/drop, runway/show, graduate portfolio, or competition? Purpose changes the commercial-vs-conceptual balance.
2. **Brand DNA** — What signature codes (shapes, fabrics, colors, details) must carry through every season?
3. **Customer and market level** — Who buys it, at what price (→ **fashion-market-research**).
4. **Season and delivery** — e.g., SS27, one drop or multiple deliveries.
5. **Size of the collection** — Number of looks (show) or options/SKUs (commercial). If unknown, recommend one.
6. **Constraints** — Budget, fabric minimums, factory capabilities, sustainability commitments.

## The Collection Development Process

```
1. Research → 2. Concept → 3. Mood & Stories → 4. Design Development
   → 5. Edit & Range Plan → 6. Cohesion Review → 7. Presentation → 8. Tech Packs & Sampling
```

### 1. Research

Two types of research feed every strong collection:

- **Primary (inspiration) research** — the creative source: art, architecture, nature, history, a place, a subculture, a personal story, archive garments, film, music, craft technique. Go deep on one source rather than shallow on many. Collect drawings, photos, fabric manipulations, found objects, and archive references.
- **Contextual (market) research** — trends (→ **fashion-trend-forecasting**), competitors and price points (→ **fashion-market-research**), customer needs.

Document research in a sketchbook or digital research book: images, annotations, first sketches, fabric experiments.

### 2. Concept

The concept is the **one idea** every decision is tested against. Write it before designing.

**Concept statement formula:**

```
[Collection name] explores [inspiration source] through [the designer's lens / point of view],
translated into [key design language: shapes, materials, techniques]
for [customer] who [need / desire / moment].
```

A strong concept is:

- **Specific** — "the uniforms of 1970s Egyptian railway workers, softened for city life" beats "nostalgia"
- **Visual** — it suggests shapes, colors, and textures immediately
- **Generative** — it can produce 20+ design ideas without repeating
- **Relevant** — it connects to the customer and the moment (macro trend)
- **On-brand** — it evolves the brand DNA rather than replacing it

Give the collection a **name** that evokes the concept.

### 3. Mood Board & Stories

Translate the concept into boards. Templates in [concept-and-boards.md](references/concept-and-boards.md).

- **Mood / concept board** — 10–20 images capturing atmosphere, not garments to copy; include the concept statement and 3–5 keywords
- **Color story** — 6–10 colors with physical standards (Pantone TCX / Coloro), proportioned by role:
  - **Base neutrals** (~50–60% of units) — anchor and connect every look
  - **Mid tones** (~25–35%) — carry the concept
  - **Accents / pops** (~5–15%) — energy and hero pieces
- **Fabric / material story** — 6–12 fabrics with swatches, composition, weight, hand-feel, and role (tailoring, fluid, structured, knit, novelty). Balance weights and textures; include at least one hero fabric that expresses the concept.
- **Silhouette story** — 3–5 key silhouettes (e.g., long lean column, cocooned volume, sharp cropped jacket) that define the collection's shape
- **Details & trims story** — the repeated signature details: a closure, a seam treatment, a pocket, a print motif, a hardware finish

### 4. Design Development

- **Sketch volume** — generate far more than you need (commonly 3–5× the final count). Explore variations systematically: change one variable at a time (length, volume, neckline, fabric, detail).
- **Drape and toile** — test key silhouettes on the stand in calico/muslin; photograph and iterate
- **Fabric manipulation** — develop signature techniques (pleating, smocking, print, embroidery, dye, cut-work) as sampled swatches
- **Line-up drawings** — draw all candidate looks side by side at the same scale; this is how cohesion is judged

### 5. Edit & Range Plan

Editing is where collections are made. Full range-planning method in [range-planning.md](references/range-planning.md).

**Range plan structure** — balance across these roles:

| Role | Purpose | Share of options (commercial) |
|---|---|---|
| **Hero / statement** | Concept at full volume; press, campaign, halo | ~10–20% |
| **Key / fashion** | Concept translated commercially; seasonal best sellers | ~30–40% |
| **Core / essentials** | Brand basics updated in season color/fabric; volume and repeat buyers | ~40–50% |

Also balance:

- **Categories** — tops, bottoms, dresses, outerwear, knitwear, accessories, per the customer's wardrobe needs
- **Price architecture** — entry, core, and hero price points (→ **fashion-market-research**)
- **Occasions** — day, work, evening, weekend
- **Deliveries** — split the range into drops with a mini-story each
- **Fabric and color efficiency** — reuse fabrics across multiple styles to meet minimums and create cohesion

**Collection size rules of thumb:**

- Capsule / first collection: ~8–15 styles
- Emerging designer seasonal: ~20–40 styles
- Graduate / show collection: often 6–12 looks
- Established brand seasonal: can be 100+ SKUs across deliveries

Start smaller than feels comfortable — fewer, better-executed styles beat a big range with thin development.

### 6. Cohesion Review (the "Collection Collective")

A collection is cohesive when any single piece is recognizable as part of the family, and the full line-up reads as one story. Test with the cohesion scorecard:

| Thread | Question | Pass when |
|---|---|---|
| **Concept** | Does every look express the concept? | You can explain each look's link in one sentence |
| **Color** | Does the palette flow across the line-up? | Colors repeat across looks; no orphan colors used only once (unless a deliberate hero) |
| **Fabric** | Are fabrics shared across styles? | Each fabric appears in 2+ styles |
| **Silhouette** | Do shapes relate? | Key silhouettes recur and evolve; volumes balance across the line-up |
| **Details** | Are signature details repeated? | Each signature detail appears in 3+ pieces in varied forms |
| **Styling** | Do the looks share a styling language? | Consistent hair, makeup, shoes, and accessory approach |
| **Brand DNA** | Is the brand recognizable? | A customer could identify the brand without the label |
| **Rhythm** | Does the line-up have flow? | Order builds: e.g., light to dark, simple to complex, day to evening, with hero looks at key points |

**Common cohesion fixes:**

- An orphan look → repeat its color, fabric, or detail elsewhere, or cut it
- Too repetitive → vary proportion and length while keeping color/fabric threads
- Concept disappears in commercial pieces → add one signature detail (a trim, a stitch, a print placement) to core styles
- Line-up feels random → reorder by color gradient or silhouette evolution

### 7. Presentation

- **Line-up** — all looks drawn or photographed in running order
- **Lookbook** — styled, photographed looks for press and buyers (→ **fashion-styling**, **image**)
- **Line sheet** — wholesale document: flat, style number, name, colorways, fabric, sizes, wholesale price, MSRP, delivery window, MOQ
- **Collection statement** — the concept statement plus 2–3 paragraphs on inspiration, materials, and craftsmanship for press and e-commerce (→ **copywriting**)
- **Portfolio (students/designers)** — research → concept → development → final line-up → technical flats → photographs, in that narrative order

### 8. Tech Packs & Sampling

Hand the edited range to production: a tech pack per style (→ **tech-pack**), sampling plan with deadlines, and costing against target prices.

## Critical Path (commercial seasonal collection)

Approximate backward plan from delivery; compress for fast-to-market brands.

| Weeks before delivery | Milestone |
|---|---|
| 52–40 | Research, trend direction, concept |
| 40–34 | Color and fabric story, fabric sourcing |
| 34–28 | Design development, range plan draft |
| 28–24 | Tech packs, proto samples |
| 24–18 | Fit sampling, costing, line review, final range |
| 18–14 | Salesman samples, lookbook, line sheet, selling (wholesale market weeks) |
| 14–4 | Bulk fabric, production, PP and TOP samples |
| 4–0 | Shipping, delivery, launch marketing (→ **launch**) |

## Common Mistakes

- **Designing before the concept is written.** Without the test sentence, anything goes and cohesion collapses.
- **Copying the mood board.** Inspiration images are for mood, not garments to reproduce.
- **Too many colors and fabrics.** Minimum orders, cost, and cohesion all suffer. Fewer, repeated materials read stronger.
- **All hero, no core.** Show-stoppers get press; core pieces pay the bills.
- **No editing.** Kill darlings that don't serve the story or the customer.
- **Ignoring the brand DNA.** Each collection should evolve the brand, not reinvent it every season.
- **Forgetting production reality.** Confirm fabric minimums, factory capabilities, and cost before falling in love with a design.

## Related Skills

- **fashion-trend-forecasting** — trend direction and color forecasting that feed the concept
- **fashion-market-research** — customer, competitors, price architecture
- **fashion-styling** — color science, proportion, lookbook styling
- **tech-pack** — production specifications per style
- **launch** — launching the collection or drop
- **copywriting** — collection statement, product descriptions
- **social** / **influencer-marketing** / **public-relations** — collection storytelling and press
