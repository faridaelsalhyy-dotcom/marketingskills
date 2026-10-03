# Campaigns and Pro Ads

## Campaign Architecture (per drop)

```
BRAND WORLD → DROP CONCEPT → CAMPAIGN → AD CONCEPTS → AD VARIANTS
```

A **campaign** serves one drop with one idea. Each campaign has three phases:

| Phase | Window | Objective | Primary KPI | Spend role |
|-------|--------|-----------|-------------|-----------|
| **Tease** | T-21 → T-1 | List/WhatsApp growth, hook discovery | Cost per lead, 3-s hold, shares | Small test budget on organic winners |
| **Launch** | T0 → T+7 | Purchases | CAC vs allowable CAC, CVR | Majority of drop budget |
| **Sustain** | T+8 → T+45 | Efficiency, proof, retargeting | CAC, repeat, sell-through | Taper to winners; hold back stock-based urgency honestly |

## Campaign Brief Template

```
CAMPAIGN ID / DROP:     CMP-D1-LAUNCH / D1
CORE IDEA (one line):   The Type B truth this drop expresses
WHO:                    Primary audience · secondary audience · what she's doing when she sees it
OFFER:                  Price · bundle · limited-stock framing · shipping/COD terms · returns
PROOF:                  Fit, fabric, reviews, UGC, press, numbers (only true ones)
STOCK REALITY:          Units available per size; cap on scale before stockout
BUDGET (ASSUMPTION):    Total · split brand/performance · test reserve · retargeting
TARGETS:                Allowable CAC · target CVR · target AOV · contribution profit target
CREATIVE PLAN:          # concepts × # hooks × # formats (see portfolio below)
LANDING PATH:           Ad → drop page / PDP → checkout; page requirements
TRACKING:               UTMs · Pixel + CAPI events · attribution window
DECISION RULES:         Scale / hold / kill rules (see media-buying-plan.md)
RETRO DATE:             T+14 and T+45
```

## Pro Ads: Concept Portfolio (not 20 clones)

For each campaign, build a **portfolio** across these axes and make sure each concept differs on at least two:

| Axis | Options |
|------|---------|
| Hook | Recognition · confession · POV · problem/solution · founder statement · social proof |
| Format | Reel/UGC video · static carousel · single image · editorial still · product demo · story |
| Voice | Founder · creator · customer · narrator/Type B voice · no voice (music + text) |
| Setting | Home chaos · street · mirror/fitting · studio editorial · event/going-out |
| Product role | Hero · styled in context · fit/fabric detail · bundle |
| Emotion | Funny · confident · nostalgic · rebellious · cozy |

Starting portfolio for a launch (assumption; scale by budget): **5 concepts × 2 hooks × 2 formats = 20 variants**, but stop and evaluate after the first 5–8 reach decision-quality spend.

## Pro Ad Description Template

```
AD ID:           AD-D1-007-v1  (links to content_id)
CONCEPT NAME:    "Five Minutes"
OBJECTIVE / STAGE: Purchases · prospecting (broad)
FORMAT / SPECS:  9:16 video 20s; 4:5 cut; 1:1 cut. Safe zones respected; captions burned in.
HOOK (0–3 s):    Visual + line + on-screen text
STORY ARC:       Hook → chaos relatable beat → product reveal → fit/style moment → CTA
PRODUCT SHOTS:   Required angles: front/back/movement/fabric detail/size reference
PRIMARY TEXT:    (Version A/B) 2–3 short lines, TYPE B voice, one clear claim
HEADLINE:        ≤ 40 chars; offer or product truth
DESCRIPTION:     Shipping/COD/returns reassurance if applicable
CTA BUTTON:      Shop Now
DESTINATION:     URL with UTMs (utm_source=meta, utm_medium=paid, utm_campaign=CMP-D1-LAUNCH, utm_content=AD-D1-007-v1)
CLAIMS CHECK:    Every claim is true and provable (fabric, sizing, delivery)
EXPECTED READ:   What metric should this move (hook rate, CTR, CPA)? What result kills it?
```

**Mockup of the finished ad (spec for the designer/editor):**

```
┌────────────────────┐
│ [0–3s] Messy floor, │   VO: "I said five minutes."
│ clothes everywhere, │   Text: "five minutes. (it's been 40)"
│ she holds the SET   │
├────────────────────┤
│ [3–10s] Quick cuts  │   Beat: 3 outfit attempts, fails, sarcasm
├────────────────────┤
│ [10–17s] Set reveal │   Fabric close-up · move · mirror check
├────────────────────┤
│ [17–20s] End card   │   Product + price/offer + "Shop the set"
└────────────────────┘
```

## Copy Rules for TYPE B

- Voice: sarcastic, warm, self-aware, never cruel. Humor beats hype.
- One idea per ad. Lead with the girl, not the garment, then land the garment.
- Specifics beat adjectives (fabric, fit, details, delivery time).
- No false scarcity. Use real unit counts or drop closing dates.
- Pull exact customer language from DMs, comments and reviews (log in `11_RESEARCH/gen-z`).

## Retargeting and Retention Ads

- **Viewers/engagers/add-to-cart/checkout starters** (Meta custom audiences, with the actual windows from the account): proof, size help, shipping/COD reassurance, "last pieces" only when true.
- **Past buyers:** cross-sell the next drop, styling content, early access.
- Exclude purchasers from prospecting. Cap frequency; watch fatigue.

## Launch Checklist (ads side)

- [ ] Pixel + CAPI firing; events deduplicated (`event_id` matches); test events verified
- [ ] UTMs on every ad; naming convention applied
- [ ] Domain verified; aggregated event priorities set per current Meta guidance
- [ ] LP: mobile speed, sizes, shipping/COD, returns above the fold
- [ ] Stock per size loaded; low-stock behavior defined
- [ ] 8+ creatives approved; claims checked
- [ ] Budget, allowable CAC, kill/scale rules written in `Campaigns` tab
- [ ] Day-1/3/7 review slots in calendar
