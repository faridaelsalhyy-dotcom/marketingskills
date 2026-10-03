# Skills Map and Resource Stack

## Competency Tiers

**Tier 1 — core now:** financial modeling · unit economics · cash-flow forecasting · media buying · marketing attribution · creative analytics · Shopify/e-commerce analytics · inventory management · demand forecasting · pricing strategy · brand strategy · fashion merchandising · consumer research · SQL/data analytics · executive decision-making.

**Tier 2 — once there is data:** media-mix modeling · customer LTV · cohort analysis · predictive inventory · advanced forecasting · data-warehouse design · automated BI · incrementality testing.

**Tier 3 — scale:** BigQuery/Snowflake · sophisticated ETL · automated financial reconciliation · advanced experimentation · predictive models · multi-channel attribution.

## Domain Coverage

| Area | Competencies |
|------|--------------|
| Business/CEO | decisions, business model, scenarios, unit economics, P&L/cash flow, pricing, working capital, forecasting, KPI design, risk, experiments |
| Finance | gross/contribution margin, CAC payback, LTV, break-even, cash conversion cycle, runway, inventory economics, drop P&L |
| Marketing | brand, performance, media buying, Meta/TikTok/Google, attribution, CAC/CPC/CPM/CTR/CVR/ROAS/MER, creative testing/fatigue, funnel analytics, CAPI, UTMs, CRM |
| Fashion/DTC | product development, merchandising, assortment, drops, pricing architecture, production planning, MOQ, suppliers, inventory, sell-through, reorder, Gen-Z behavior |
| Data | SQL, Python, cleaning, modeling, ETL/ELT, APIs, dashboards, cohorts, A/B tests, forecasting, warehouses |
| Technology | Shopify + APIs, Meta Marketing API, TikTok APIs, GA4, Google Ads API, BigQuery, Looker Studio, Airtable/Notion APIs, webhooks, Git/GitHub, automation |
| Brand/Creative | world-building, creative direction, content strategy, art direction, voice, campaigns, UX/UI, e-commerce IA, storytelling |

## GitHub Is Implementation Infrastructure, Not a Library Dump

GitHub is strongest for code, data models, API patterns, dashboards and technical workflows. Keep brand research, books, market reports, Meta and Shopify documentation in a **research knowledge base** (Notion/Docs/`11_RESEARCH`) next to it.

Search topics by area:

| Area | Topics |
|------|--------|
| BI | business-intelligence · data-analytics · kpi-dashboard · financial-dashboard · ecommerce-analytics · retail-analytics · customer-analytics |
| E-commerce | shopify-api · shopify-analytics · shopify-app · shopify-admin-api · shopify-webhooks · ecommerce-data |
| Marketing analytics | marketing-attribution · marketing-mix-modeling · media-mix-modeling · marketing-analytics · customer-acquisition · meta-ads-api · facebook-marketing-api · tiktok-marketing-api · google-ads-api |
| Customer | customer-lifetime-value · cohort-analysis · retention-analysis · customer-segmentation · churn-analysis · purchase-frequency |
| Inventory/Supply | inventory-management · inventory-optimization · demand-forecasting · supply-chain-analytics · reorder-point · safety-stock · inventory-forecasting |
| Finance | financial-modeling · cash-flow-forecasting · unit-economics · profitability-analysis · budget-forecasting |

Vet any repository before relying on it: license, maintenance, tests, whether it is stdlib-light, and whether its assumptions fit a small Egyptian DTC brand. Never run unreviewed code against live credentials.

## Extraction Method: Repository → Skill → Business Application → TYPE B Application

For every resource, produce this card rather than "this repo does X":

```
RESOURCE:               name · link · license · last commit
METHOD:                 what it computes and how
DATA REQUIRED:          fields, volume, history length
WHEN APPROPRIATE:       statistical/business conditions
LIMITATIONS:            where it breaks
BUSINESS APPLICATION:   which decision it improves
TYPE B APPLICATION:     what TYPE B needs first (data, volume) and the concrete use
STAGE:                  NOW / NEXT / SCALE
```

Examples:
- **MMM repo →** what MMM does → needs long weekly history across several channels → not appropriate at small spend/one channel → TYPE B waits (SCALE) and uses simple holdout/time-based tests meanwhile → decision improved: cross-channel budget split.
- **Reorder-point code →** formula and assumptions → TYPE B inputs: actual supplier lead time, MOQ, Egyptian fabric availability, cash constraint, demand volatility from first drops → decision improved: reorder quantity and timing.

## Priority Order to Build

1. Master Sheet (Products, Drops, Cash, Content, Decision Log)
2. Landed cost + allowable CAC (gate for any ad spend)
3. Shopify + Meta read sync, then Reconciliation
4. Content tracker and creative test log
5. Weekly rhythms (media review, finance close, content review)
6. Looker Studio dashboard, CRM flows, CAPI hardening
7. Cohorts/LTV, forecasting, warehouse
