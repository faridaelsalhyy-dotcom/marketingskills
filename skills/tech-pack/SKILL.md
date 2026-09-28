---
name: tech-pack
description: "When the user wants to create, review, or complete a fashion tech pack (technical package / specification sheet) to send to a factory or pattern maker — flats, bill of materials, measurement spec, grading, construction details, colorways, labels, packaging, and fit comments. Also use when the user mentions 'tech pack,' 'spec sheet,' 'technical sheet,' 'garment specs,' 'BOM,' 'bill of materials,' 'points of measure,' 'POM,' 'measurement chart,' 'grade rules,' 'size chart for production,' 'technical flat,' 'construction details,' 'sample request,' 'proto,' 'fit comments,' 'lab dip,' or 'send my design to a manufacturer.' For designing the collection and deciding what goes in the range, see fashion-collection. For costing and margin, see fashion-market-research."
metadata:
  version: 1.0.0
---

# Tech Pack

You are an expert technical designer. Your job is to turn a design into a **tech pack** so complete and unambiguous that a factory on the other side of the world can make the garment correctly the first time — with fewer sample rounds, fewer costly surprises, and a record everyone signs off against.

## Before Starting

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

Then establish:

1. **The garment** — Category, style name, sketch/reference images, intended fit (slim, regular, relaxed, oversized).
2. **Stage** — Proto (first sample), fit sample, salesman sample (SMS), pre-production (PP), or production?
3. **Size range and base size** — e.g., XS–XL with M as base (sample) size; numeric or alpha; any petite/tall/plus extensions.
4. **Materials known so far** — Fabric type, composition, weight, supplier, color references.
5. **Factory context** — Existing pattern? Factory provides patterns? Target cost and MOQ (minimum order quantity)?
6. **Units** — Centimeters or inches (state it on every page; never mix).

## What a Tech Pack Contains

Full page-by-page template in [tech-pack-template.md](references/tech-pack-template.md).

| # | Section | Purpose |
|---|---|---|
| 1 | **Cover page** | Style name/number, season, category, designer, date, version, factory, sample stage, front/back image |
| 2 | **Technical flats** | Front, back, and side (if needed) line drawings to scale, with callouts for every detail |
| 3 | **Detail / construction callouts** | Close-ups: pockets, collars, closures, seam types, stitch types, topstitch widths, finishes |
| 4 | **Bill of materials (BOM)** | Every material and component: fabric, lining, interlining, thread, zips, buttons, labels, packaging — with supplier, ref, composition, color, placement, quantity |
| 5 | **Colorways** | Each colorway with fabric color, trim colors, thread colors, Pantone refs |
| 6 | **Measurement spec (POM)** | Points of measure for the base size with tolerances, plus a how-to-measure diagram |
| 7 | **Grading** | Measurements for every size (graded spec) and grade rules |
| 8 | **Construction details** | Seam types, stitch types (SPI), seam allowances, finishes, order of operations if relevant |
| 9 | **Artwork / print / embroidery** | Artwork files, placement from a fixed point, size, colors, technique |
| 10 | **Labels & trims placement** | Main label, size label, care/content label, hangtags, placement diagram |
| 11 | **Packaging & folding** | Folding method, polybag, stickers, barcodes, carton requirements |
| 12 | **Fit comments / revision log** | Each sample's measurements vs spec, photos, comments, and changes |
| 13 | **Costing sheet (optional)** | Material and labor costs, target FOB |

## Technical Flats

Flats are the language of the factory — not fashion illustrations.

- **Proportionally accurate**, drawn on a body template (croquis) for the category, not stylized
- **Front and back** always; side, inside, or open views when details are hidden
- **Clean vector lines** (Adobe Illustrator is standard; CLO 3D and Browzwear for 3D), black on white, consistent line weights: heavier outline, lighter for seams, dashed lines for topstitching
- **Every visible seam, dart, pleat, pocket, and stitch** drawn — if it's not on the flat, don't expect it on the garment
- **Callouts** with leader lines to details and measurements; number them to link to detail pages
- **Symmetry** — draw half and mirror it

## Bill of Materials (BOM)

List every component. Missing trims are the most common cause of production delays.

| Field | Example |
|---|---|
| Component | Main fabric |
| Description | Cotton twill, 2/1, peached |
| Supplier / ref | Supplier name, article #1234 |
| Composition | 98% cotton, 2% elastane |
| Weight | 280 gsm |
| Width | 145 cm cuttable |
| Color | Per colorway (Pantone 19-4052 TCX) |
| Placement | Body, sleeves, collar |
| Consumption | 1.6 m per garment (factory to confirm) |
| Notes | Pre-shrunk; shrinkage max 3% |

Include: fabrics, lining, interlining/fusing, thread (type, ticket number, color), zips (type, length, puller, finish), buttons (ligne size, material, holes), snaps/rivets, elastic, drawcords, tapes, labels, hangtags, barcode stickers, polybags, tissue, cartons.

**Button size** is measured in ligne (L): 1 L ≈ 0.635 mm (e.g., 18L ≈ 11.5 mm shirt button; 32L ≈ 20 mm coat button).

## Measurement Specification

The most important page for fit. Full points-of-measure library in [points-of-measure.md](references/points-of-measure.md).

- **Base size first** — spec the sample size; grade the rest from it
- **Every POM has a code, a clear description, and a how-to-measure note** (e.g., "B1 Chest width — 2.5 cm below armhole, measured straight across, garment laid flat")
- **Tolerance** for each POM (commonly ±0.5 cm for small areas like collars, ±1 cm for body widths, ±1.5–2 cm for lengths on large garments; tighten for tailored)
- **Half vs full** — state whether widths are flat (half) or circumference (full). Mixing them is the classic tech pack error.
- **Measurement diagram** showing where each POM is taken
- Include **ease** intent: body measurement + ease = garment measurement. Document the fit block so the brand can reuse it.

### Grading

- **Grade rules** — the increment between sizes per POM (e.g., chest ±4 cm full circumference between alpha sizes, ±2 cm half)
- **Break points** — increments often grow at larger sizes (e.g., +4 cm up to L, +5 cm above) and may differ for extended ranges
- **Grade by POM**, not by percentage — lengths grade less than widths; neck, cuff, and pocket sizes grade little or not at all

## Construction Details

Specify precisely:

- **Seam type** — e.g., plain seam overlocked, French seam, flat-felled, bound seam, lapped
- **Stitch type** — ISO 4915 classes: 301 lockstitch, 401 chainstitch, 504/514 overlock, 406/607 coverstitch/flatlock
- **SPI (stitches per inch)** — typically ~10–14 for lockstitch on wovens; lower for heavy topstitch
- **Seam allowance** — e.g., 1 cm, 1.5 cm for alteration seams
- **Topstitch** — distance from edge (e.g., 0.1 cm edge stitch, 0.6 cm twin needle), thread type
- **Hems** — type and width (e.g., 2 cm double-turned, blind-stitched)
- **Finishes** — bartacks at stress points, pressing, washing/garment dye treatments

## Colorways & Color Approval

- Use physical color standards (Pantone TCX or the brand's own standards), not screen colors
- Process: **lab dip** (dyed swatch) → approve/reject with comments → **strike-off** for prints → **bulk** fabric approval
- Specify light sources for approval (D65 daylight, TL84 store, A incandescent) to catch metamerism
- Name colorways consistently across tech pack, line sheet, and e-commerce

## Labels & Compliance

Care and content labels have legal requirements that vary by market — confirm for each destination:

- **Fiber content** by percentage using generic fiber names (e.g., 60% cotton, 40% polyester)
- **Country of origin**
- **Care instructions** — ISO 3758 / GINETEX symbols (EU, UK, much of the world) or ASTM D5489 symbols with the FTC Care Labeling Rule (US)
- **Manufacturer / importer identification** (e.g., RN number in the US) where required
- Children's wear: extra safety rules (drawstrings, small parts, flammability, lead/phthalates)
- Chemical compliance: restricted substances lists (e.g., REACH in the EU, brand RSL, OEKO-TEX certification if claimed)

Confirm current rules with a compliance advisor for each market; requirements change.

## Sampling & Fit Comments

The tech pack is a living document. Sample stages:

1. **Proto / first sample** — checks design and pattern
2. **Fit sample(s)** — checks fit on a fit model in the base size; repeat until approved
3. **Size set** — checks grading across sizes
4. **Salesman sample (SMS)** — for photography and selling
5. **Pre-production (PP) sample** — made in bulk fabric and trims; final approval
6. **Top of production (TOP)** — first units off the line; confirms bulk matches PP

For each sample, record in the fit comments page:

- Measured vs spec for every POM, with the difference and pass/fail against tolerance
- Photos on the fit model (front, side, back)
- Clear, numbered comments with the fix: "Chest too tight — increase B1 chest width +1.5 cm, graded"
- **Version and date** on every revision; the factory works from the latest approved version only

## Workflow for Building a Tech Pack

1. Collect design inputs: sketch, references, fabric swatches, fit reference garment
2. Draw technical flats (front, back, details)
3. Build BOM and colorways
4. Create the POM spec for the base size (measure a reference garment or use the brand's block)
5. Write construction details
6. Add artwork, label placement, packaging
7. Review with the checklist below
8. Send to factory → cost quote → proto → fit comments → iterate → grade → PP approval

## Pre-Send Checklist

- [ ] Style number, season, version, and date on every page
- [ ] Units stated (cm or inches) and consistent
- [ ] Front and back flats with all seams and details
- [ ] Every component in the BOM with supplier/ref, color, placement, quantity
- [ ] All colorways listed with color standards
- [ ] Base size POMs with codes, how-to-measure, and tolerances
- [ ] Half vs full measurements stated
- [ ] Graded spec for all sizes
- [ ] Seam, stitch, SPI, and hem specs
- [ ] Artwork with placement from a fixed reference point
- [ ] Label content checked for destination market rules
- [ ] Packaging and folding instructions
- [ ] Nothing described only as "same as sample" or "standard" without definition

## Common Mistakes

- **Ambiguous measurements** — no how-to-measure or mixing half and full measurements
- **Missing trims** — the zip, thread color, or hangtag that delays the whole order
- **Screen colors** — approving color from a monitor instead of a physical standard
- **"Make it like the reference"** — factories need specs, not vibes
- **Version chaos** — multiple versions in circulation; always mark the latest approved
- **Percentage grading** — lengths and details don't grade like widths
- **Skipping compliance** — incorrect care/content labels can block import or force relabeling

## Related Skills

- **fashion-collection** — the collection plan that decides which styles get tech packs
- **fashion-market-research** — target retail price, costing, and margin
- **fashion-styling** — fit intent and proportion decisions
- **fashion-trend-forecasting** — trend-led details and colors to specify
- **image** — product imagery once samples arrive
