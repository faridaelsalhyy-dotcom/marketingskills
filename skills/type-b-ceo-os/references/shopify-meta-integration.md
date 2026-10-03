# Shopify + Meta Ads Integration (plug-in design)

Integrations arrive later. This design lets them drop in without changing formulas: connectors fill `raw_*` tabs; everything else reads those tabs.

Verify endpoint names, API versions and permission scopes against the official docs at build time (Shopify Admin API, Meta Marketing API, Meta Conversions API). They are versioned and change.

## Phases

| Phase | Capability | Writes? |
|-------|------------|---------|
| **0 — CSV** | Founder exports Shopify orders/inventory and Meta insights CSVs into the `raw_*` tabs (same columns as `assets/sheets/`) | Sheet only |
| **1 — Read** | Scheduled pull: Shopify orders, products, inventory, customers; Meta insights at ad level | Sheet `raw_*` only |
| **2 — Analyze + Update Sheets** | Agent analyzes, writes recommendations and updates input tabs (with approval) | Sheet only |
| **3 — Propose changes** | Agent drafts ad-account/store changes (budgets, pauses, new ad sets, product edits) as a **change request** | None until approved |
| **4 — Execute (optional)** | Founder-approved, logged, reversible changes via API | Store/ad account, per-change approval |

**Hard rule:** no write to Shopify or Meta without explicit approval in the session. Every change is logged in `Decision_Log` with old value, new value, reason and rollback.

## Shopify Data Flow

| Need | Source | Lands in |
|------|--------|----------|
| Orders, line items, discounts, refunds, UTMs/landing site, new vs returning | Admin GraphQL API orders/refunds (or Shopify Flow / scheduled export for NOW) | `raw_shopify_orders` |
| Products, variants, price, cost per item | Products + inventory item `cost` | `Products` cross-check |
| Inventory by variant/location | Inventory levels | `raw_shopify_inventory` |
| Customers, first/repeat order | Customers/orders | cohort calc (NEXT) |
| Real-time triggers | Webhooks: orders/paid, refunds/create, inventory_levels/update, products/update | refresh a row or alert |
| Reporting queries | ShopifyQL (where available on the plan) | spot checks vs sheet |

Requirements: a custom app with **read-only scopes first** (orders, products, inventory, customers); add write scopes only at Phase 4. Store tokens in a secrets store, never in the sheet or repo. Backfill history once, then incremental by `updated_at`, deduplicating on order ID.

Order-line normalization (feeds `raw_shopify_orders`): one row per line item; `net_sales = gross − discounts − returns`; flag `is_new_customer`; parse `utm_*` from landing URL; map `sku → drop_id` via `Products`.

## Meta Ads Data Flow

| Need | Source | Lands in |
|------|--------|----------|
| Spend, impressions, reach, frequency, clicks, link clicks, CTR, CPC, CPM | Marketing API `/{ad_account}/insights` at `level=ad`, `time_increment=1` | `raw_meta_insights` |
| Funnel actions (landing page view, add to cart, initiate checkout, purchase) and action values | `actions`, `action_values` fields | same |
| Creative metadata (name, ids, creative asset) | Ads/creatives endpoints | `Creative_Tests` |
| Breakdowns (placement, age, gender, device) | Insights breakdowns, only when diagnosing | ad-hoc tab |
| Video hook/hold | Video play-action fields (3-s plays, ThruPlays) | same |

Requirements: system user or app token with `ads_read` first; `ads_management` only at Phase 4. Use daily pulls plus a rolling re-pull of the last 3–7 days because platform numbers restate as attribution settles. Record `attribution_setting` with each pull.

## Tracking Layer (Pixel + CAPI)

- Fire the same events from the browser Pixel and the server (Conversions API): ViewContent, AddToCart, InitiateCheckout, Purchase.
- **Deduplicate** with an identical `event_id` and event name on both sides.
- Send hashed customer parameters (email/phone, per Meta's normalization/hashing rules) plus `fbp`/`fbc` where available; respect consent and local privacy rules.
- Monitor Event Match Quality and dedup rate in Events Manager.
- Shopify's native Facebook & Instagram channel sets up Pixel + CAPI; confirm what it sends before adding a custom server.
- Add UTMs on every ad: `utm_source=meta · utm_medium=paid · utm_campaign={campaign} · utm_content={ad}` so Shopify orders can be tied back to ads independent of Meta's own attribution.

## Reconciliation Job (weekly, and whenever numbers disagree)

| Check | Rule |
|-------|------|
| Meta purchases vs Shopify orders with `utm_source=meta` | Gap expected; investigate if it widens |
| Meta revenue vs Shopify net sales | Meta is gross, window-attributed; Shopify is net of refunds |
| Spend vs bank/card statement | Platform spend vs billing date |
| Time zones | Align ad account TZ and store TZ before comparing days |
| Currency | One currency in the sheet; label FX source/date |

Output is a short table of differences with causes and **which number to use for which decision**.

## Agent Jobs (what the agent does once connected)

| Job | Cadence | Output |
|-----|---------|--------|
| Sync check | Daily | Last-sync times; anomalies (missing days, duplicates) |
| Daily brief | Daily | Dashboard (cash, sales, marketing, inventory, actions) |
| Creative fatigue scan | Daily | Flags where frequency ↑, CTR ↓, CPA ↑ |
| Stock vs spend check | Daily | Spend heading to a stockout; days of inventory by variant |
| Weekly media review | Weekly | Funnel diagnostic, budget proposals, test queue |
| Weekly finance close | Weekly | Drop P&L, cash forecast refresh, margin check |
| Drop retro | After each drop | Learning loop one-pager; benchmark updates |
| Change requests | On demand | Proposed budget/pause/new-test list with expected effect and rollback |

## Change Request Format (Phase 3–4)

```
CHANGE:    Increase AD-SET D1_SALES_SCALE_BROAD budget  from X → Y /day
WHY:       CAC <value> vs allowable <value> for <n> days, n purchases; stock covers <n> days at new pace
RISK:      CAC drift, stockout of size M, cash float <value>
ROLLBACK:  Return to X; re-evaluate after 72h
SUCCESS:   CAC ≤ allowable and MER ≥ target after 5 days
APPROVAL:  [ ] founder
```

## Data Privacy

Customer PII stays in Shopify. The sheet and analysis carry order IDs and aggregates, not names/emails/phones. Hash before sending anything to Meta CAPI. Do not paste credentials or tokens into chats, sheets or commits.

## Tool Options by Stage

| Stage | Sync approach |
|-------|---------------|
| NOW | Manual/CSV or Sheets add-ons; Shopify native reports; Ads Manager exports |
| NEXT | Scheduled script/automation (Make, Zapier, or small stdlib/Node script); Looker Studio connectors; Klaviyo |
| SCALE | Warehouse (BigQuery) with ELT, then dashboards; MMM/incrementality |

See also `tools/integrations/shopify.md`, `tools/integrations/meta-ads.md`, and `tools/composio/marketing-tools.md` in this repo for connector and MCP routes.
