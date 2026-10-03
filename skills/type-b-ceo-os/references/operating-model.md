# Operating Model

## System Folders (Workspace / Repo / Notion Layout)

```
TYPE-B-CEO-OS/
├── 01_CEO/         decision-frameworks · scenario-planning · strategic-planning · decision-log
├── 02_FINANCE/     cash-flow · unit-economics · pricing · forecasting · drop-pnl
├── 03_MARKETING/   media-buying · attribution · creative-analytics · funnel-metrics
├── 04_BRAND/       brand-strategy · brand-world · consumer-research · creative-direction
├── 05_PRODUCT/     product-development · merchandising · pricing · drop-planning
├── 06_PRODUCTION/  suppliers · production · quality-control · landed-cost
├── 07_INVENTORY/   inventory · demand-forecasting · sell-through · reorder-points
├── 08_CONTENT/     content-calendar · creative-testing · content-performance · content-roi
├── 09_ECOMMERCE/   shopify · conversion-rate · product-pages · customer-experience
├── 10_DATA/        data-models · sql · dashboards · automation
└── 11_RESEARCH/    fashion · egypt · gen-z · competitors · case-studies
```

Each folder holds **one responsibility**. No folder tries to own everything. Code, schemas and API patterns live in `10_DATA`; research (articles, books, Meta/Shopify docs, market reports) lives in `11_RESEARCH` as notes, not as a code dump.

## Stages: NOW → NEXT → SCALE

| Stage | Stack | You need | Move up when |
|-------|-------|----------|--------------|
| **NOW** (pre-launch to first drops) | Google Sheets Master Sheet, Shopify, Meta Ads Manager, a Notion/Sheet decision log | Landed cost, drop P&L, 30-day cash forecast, content tracker, weekly ad read | ≥ ~100 orders/month for 2 consecutive months, or ad spend ≥ ~20% of monthly revenue |
| **NEXT** (repeatable sales) | + Looker Studio, Klaviyo (or WhatsApp/SMS flows), Meta Pixel + CAPI, strict UTMs, Shopify→Sheet sync | Cohorts, repeat rate, creative-level CAC, 90-day cash forecast | ≥ 2 sales channels with real spend, or ≥ 4 active SKUs/drop cadence, or a hire needs shared dashboards |
| **SCALE** (multi-drop, multi-channel) | + BigQuery, automated reconciliation (A2X/Link My Books or Xero/QuickBooks), MMM, incrementality tests | Warehouse, predictive inventory, MMM | Decide only with data volume to justify it; do not buy enterprise tooling early |

The thresholds are starting points, not laws. State them as such and adjust to her actual numbers.

## CEO KPI Tree

```
NORTH STAR: Profitable brand growth
├─ Demand ........ reach · engagement · site sessions · branded search
├─ Conversion .... CVR · AOV · orders
├─ Acquisition ... CAC · CPC · CTR · CPM · ROAS · MER
├─ Economics ..... COGS · contribution margin · contribution profit
├─ Operations .... inventory · lead time · defect rate
├─ Cash .......... cash flow · runway · working capital
└─ Brand ......... recognition · community · repeat purchase · loyalty
```

## Core Formulas

| Metric | Formula |
|--------|---------|
| CAC (blended) | Total acquisition spend ÷ new customers |
| CPC / CTR / CPM | Spend ÷ clicks · Clicks ÷ impressions · Spend ÷ impressions × 1000 |
| CVR | Orders ÷ sessions |
| ROAS | Ad-attributed revenue ÷ ad spend |
| MER | Total revenue ÷ total marketing spend |
| Landed cost / unit | (Factory + fabric + trims + packaging + freight + customs + duties + port + local transport + other direct) ÷ units received (use **good** units) |
| Contribution profit | Net revenue − COGS − payment fees − shipping subsidy − fulfillment − variable marketing |
| **Allowable CAC** | Contribution profit per order **before** ad spend × target share kept (e.g. break-even = 100%, growth mode = 70–90%) |
| Defect rate | Defective units ÷ total units |
| Sell-through | Units sold ÷ units received |
| Days of inventory | Units on hand ÷ avg daily unit sales |
| Reorder point | Avg daily sales × lead time + safety stock (then check cash, MOQ, spike plans) |
| Runway | Deployable cash ÷ avg monthly net burn |
| Deployable cash | Cash − committed obligations − upcoming production − operating costs − marketing commitments |

Show the worked calculation every time, with the founder's real inputs.

## Product Situation Classes (descriptive, not auto-kill)

Profitable + strong demand · profitable + weak demand · low margin + strong demand · low margin + weak demand · high CAC · high conversion · inventory risk · production risk · brand-building product. Never scale or kill on one metric.

## Red Flag Logic

| Flag | Fires when | First check |
|------|-----------|-------------|
| Cash | Cash < committed obligations within horizon | Move/delay production or spend? |
| CAC | Rolling-7d CAC > allowable CAC for 3+ days with ≥ ~30 clicks/ad-set/day volume | Creative, offer, LP, tracking |
| Margin | Contribution margin < target | Discounts, shipping subsidy, returns, price |
| Inventory velocity | Sell-through pace < plan by a set % | Price, demand, creative, stock-size mix |
| Stockout | Days of inventory < lead time + safety days | Reorder economics, cash, MOQ |
| Creative fatigue | Frequency ↑ while CTR ↓ and CPA ↑ together | Refresh hook/format, not just copy |
| Production | Actual lead time > historical avg | Supplier comms, fabric, QC |
| Revenue quality | Revenue ↑ while contribution profit ↓ | Mix, discounts, CAC creep |
| Discount | Growth mostly in discounted orders | Full-price demand health |

Each alert prints: **what fired → data → likely causes → decision needed → owner → deadline.** Suppress anything that needs no action.

## Decision Log (one row per important decision)

`Date · Decision · Why · Data used · Assumptions · Alternative considered · Decision maker · Expected outcome · Actual outcome · Lesson · Review date`

Set a **review date** on every decision. Write the **"change my mind if…"** trigger in the Assumptions cell.

## Learning Loop (after every drop, campaign or production run)

What happened → why → what we expected → where we were wrong → what worked → what failed → what changes → what stays → what to test next. Store as a one-page retro tied to the drop ID; update benchmark cells (lead time, defect rate, CAC range, CVR range) from actuals.

## Scenario Template (major decisions)

| | Conservative | Base | Upside |
|--|--:|--:|--:|
| Units sold | | | |
| Revenue | | | |
| CAC / AOV / CVR | | | |
| Marketing spend | | | |
| COGS | | | |
| Contribution profit | | | |
| Ending inventory | | | |
| Cash remaining | | | |

Mark every input as **actual**, **assumption** or **benchmark (source, date)**.
