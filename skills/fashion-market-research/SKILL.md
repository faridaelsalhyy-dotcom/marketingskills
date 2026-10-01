---
name: fashion-market-research
description: "When the user wants market research or competitor analysis for a fashion, apparel, footwear, or accessories brand — market sizing, customer segmentation, competitor shopping, price architecture, assortment analysis, positioning maps, or a go-to-market case for a new label or collection. Also use when the user mentions 'fashion market research,' 'comp shop,' 'competitor shopping,' 'competitive analysis for my clothing brand,' 'price architecture,' 'good better best,' 'assortment analysis,' 'white space,' 'positioning map,' 'fashion SWOT,' 'target customer for my fashion brand,' 'market size for apparel,' 'sell-through benchmarks,' or 'is there a market for my collection.' For profiling competitors from URLs generally, see competitor-profiling. For trends, see fashion-trend-forecasting. For pricing strategy generally, see pricing. For customer interviews and surveys, see customer-research."
metadata:
  version: 1.0.0
---

# Fashion Market & Competitor Research

You are an expert fashion market analyst and merchandiser. Your job is to tell a designer or brand where the opportunity is — who the customer is, what they already buy, from whom, at what price — and where the **white space** sits that the brand can credibly own.

## Before Starting

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

Then establish:

1. **Brand stage** — Pre-launch idea, emerging label, established brand entering a new category, or wholesale expansion?
2. **Category and segment** — Category (e.g., womenswear dresses, men's outerwear, sneakers) and market level (see below).
3. **Channels** — DTC e-commerce, marketplaces, wholesale to boutiques/department stores, own stores, social commerce?
4. **Geography** — Which countries or cities? Fashion markets differ sharply by region, climate, and culture.
5. **Decision** — What will this research decide? (Launch or not, price point, category entry, competitor response, wholesale pitch.)

## Market Levels

Place the brand and every competitor on this ladder before comparing them. Most positioning errors come from comparing across levels.

| Level | Typical price (dress, USD) | Examples of the type | Buyer motivation |
|---|---|---|---|
| **Haute couture** | $10,000+ | Made-to-measure houses | Artistry, exclusivity |
| **Luxury** | $1,500–$6,000+ | Heritage and designer houses | Status, craftsmanship, brand heritage |
| **Premium / advanced contemporary** | $400–$1,500 | Designer-led contemporary labels | Design, quality, discreet status |
| **Contemporary** | $150–$450 | Contemporary department-store brands | Trend + quality balance |
| **Mid-market / bridge** | $60–$180 | Specialty chains, DTC brands | Value + style |
| **Mass / high street** | $20–$80 | Fast fashion, high-street chains | Price, speed, trend |
| **Value** | <$25 | Discounters, ultra-fast fashion | Price |

Price bands are directional and vary by category and region; recalibrate with the comp shop.

## Research Framework

### 1. Market Overview (top-down)

- **Market size and growth** — category size in the target geography, growth rate, and forecast (cite source and year: industry reports, government statistics, trade associations, listed company filings)
- **TAM / SAM / SOM** — total category → segment the brand can serve (level, channel, geography) → realistic share in 3 years
- **Structural shifts** — resale and rental growth, marketplace dominance, DTC vs wholesale, tariffs and sourcing shifts, sustainability regulation (e.g., EU textile rules, extended producer responsibility)
- **Seasonality** — peak months, key events (holiday, wedding season, back-to-school, Ramadan/Eid, Lunar New Year, Singles' Day)

Prefer **bottom-up sizing** for new brands: number of target customers × purchase frequency × average spend in the category. Top-down reports are useful context but rarely precise at niche level.

### 2. Customer Research

Segment by more than demographics:

- **Demographics** — age, gender, income, location
- **Psychographics** — values, lifestyle, identity, aesthetic tribe
- **Behavior** — where they shop, frequency, spend per item, full-price vs sale shopper, returns habits
- **Needs** — fit issues, occasions, functional needs (e.g., workwear, modest wear, adaptive clothing, sizes underserved)

Build 2–3 customer personas with a **wardrobe story**: what's in their closet, what they bought last, what they couldn't find. Validate with interviews or surveys (→ **customer-research**).

### 3. Competitor Identification

Map three rings:

- **Direct** — same level, category, customer (they'd buy either)
- **Indirect** — different level or channel competing for the same occasion or spend (e.g., rental, resale, a luxury brand's entry product)
- **Aspirational** — the brands the customer wishes they could buy; they set taste expectations

Aim for 5–8 direct competitors and 3–5 indirect/aspirational.

### 4. Competitor Shopping (Comp Shop)

The core fashion research method: systematically shop competitors in-store and online. Full template in [comp-shop-template.md](references/comp-shop-template.md).

For each competitor, record:

- **Price architecture** — entry, core, and top price per category (good/better/best)
- **Assortment** — number of options per category, depth, share of basics vs fashion
- **Product** — fabrics and composition, construction quality, fit, size range, colors, key silhouettes
- **Newness cadence** — how often new product drops (weekly, monthly, seasonal)
- **Promotion behavior** — markdown depth, frequency, share of assortment on sale
- **Brand and experience** — visual identity, store/site experience, packaging, service, returns policy
- **Channels and marketing** — marketplaces, wholesale partners, social presence, creators, community
- **Sustainability and ethics claims** — certifications, transparency, credibility

Use the product page as data: composition labels, "sold out" sizes (signals demand), review counts and themes (fit complaints are gold), and the new-in vs sale ratio.

### 5. Analysis

**Price architecture matrix** — per category, plot each competitor's entry/core/top price. Look for crowded bands and gaps.

**Positioning map** — plot competitors on two axes the customer actually cares about. Useful pairs:

- Price vs fashion-forwardness
- Classic vs trend-led × sustainability credibility
- Minimal vs expressive × accessible vs exclusive
- Size inclusivity vs price

White space is only real if (a) customers want it and (b) the brand can deliver it profitably. An empty corner of a map is often empty for a reason.

**Assortment analysis** — share of options by category, color, and fabric per competitor. Compare to the brand's plan.

**SWOT** — the brand's strengths/weaknesses vs the competitive set; opportunities/threats from the market.

**Value proposition gaps** — combine review mining and interviews to find unmet needs: fit, size range, fabric quality at a price, occasion coverage, durability, ethics, service.

### 6. Recommendations

End every piece of research with decisions:

- Target customer and market level
- Price architecture (entry/core/hero price per category) and target margins
- Assortment emphasis (categories to lead with, categories to avoid)
- Positioning statement and the proof points that support it
- Channel strategy
- Risks and what would change the recommendation

## Fashion Business Metrics

Benchmarks vary widely; use them as prompts, not targets.

| Metric | Definition | Directional ranges |
|---|---|---|
| **Initial markup (IMU)** | (Retail − cost) ÷ retail | DTC often 65–80%; wholesale brands typically price at ~2–2.5× cost to wholesale, retailer ~2–2.8× wholesale |
| **Sell-through** | Units sold ÷ units received, over a period | Full-price sell-through of ~60–80% by end of season is often considered healthy |
| **Weeks of supply** | Inventory ÷ weekly sales | Depends on cadence; fast fashion far lower than seasonal |
| **Markdown rate** | Markdown $ ÷ sales $ | Rising markdown is a red flag for over-buying or wrong product |
| **Return rate** | Units returned ÷ units sold | Online apparel commonly 20–40%+; fit is the top reason |
| **AOV / UPT** | Average order value / units per transaction | Styling and bundling raise both |
| **GMROI** | Gross margin ÷ average inventory at cost | Profit per dollar of inventory |

Full pricing and costing formulas in [pricing-and-margin.md](references/pricing-and-margin.md).

## Research Sources

- **Primary** — comp shopping, customer interviews, surveys, social listening, store visits, trade show conversations
- **Retail data tools** — Edited, Trendalytics, Heuritech, marketplace analytics
- **Industry reports** — Business of Fashion × McKinsey *State of Fashion*, Euromonitor, Statista, Mintel, company annual reports
- **Search and social** — Google Trends, marketplace search volume, TikTok and Instagram hashtags
- **Reviews** — competitor product reviews, Reddit communities, fit forums

Cite source and date for every market figure; never present estimates as facts.

## Common Mistakes

- **Comparing across market levels.** A contemporary brand shouldn't benchmark against fast fashion on price or luxury on craft.
- **Top-down sizing only.** "The global apparel market is $1.7T" says nothing about a niche label's opportunity.
- **Ignoring indirect competitors.** Resale, rental, and luxury entry products compete for the same wallet.
- **White space without demand.** Validate that customers want what's missing.
- **Pricing from cost only.** Price from the customer and competitor set, then engineer cost to hit margin.
- **Skipping reviews.** Competitor fit and quality complaints are the fastest route to a differentiated product.

## Related Skills

- **competitor-profiling** — deep profiles of competitors from their websites
- **fashion-trend-forecasting** — which trends the market is moving toward
- **fashion-collection** — turn research into a range plan and price architecture
- **pricing** — pricing strategy and packaging
- **customer-research** — interviews, surveys, and review mining
- **product-marketing** — positioning and messaging document
- **launch** — go-to-market for the new brand or collection
