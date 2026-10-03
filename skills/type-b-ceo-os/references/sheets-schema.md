# Master Sheet Schema

One Google Sheet (or Airtable/Notion DB) is the NOW-stage database. Raw tabs are filled by integrations or CSV import and never hand-edited. Everything else is a formula reading raw tabs and **Settings**, so changing an input updates the whole model.

Templates for each tab are in `assets/sheets/*.csv` (headers + one example row).

## Tab Map

| Tab | Type | Purpose |
|-----|------|---------|
| `Settings` | Input | Targets, fees, FX, thresholds, minimum cash reserve |
| `Drops` | Input + calc | Master drop tracker |
| `Products` | Input + calc | One row per SKU/variant: costs, price, margin |
| `Production` | Input | Stage tracker, dates, deposits, QC |
| `Suppliers` | Input | MOQ, lead time actuals, defect rate |
| `Inventory` | Calc | Units, velocity, days of inventory, reorder point |
| `Content` | Input | Content pipeline with cost and results |
| `Campaigns` | Input + calc | Campaign plan, budgets, results |
| `Creative_Tests` | Input + calc | Creative portfolio and fatigue |
| `Cash` | Input + calc | 7/30/90-day forecast |
| `Finance` | Calc | Drop P&L, contribution profit |
| `Decision_Log` | Input | Institutional memory |
| `Scenarios` | Input + calc | Conservative / Base / Upside |
| `Dashboard` | Calc | CEO daily command center |
| `raw_shopify_orders` | Raw | Order lines from Shopify |
| `raw_shopify_inventory` | Raw | Inventory levels |
| `raw_meta_insights` | Raw | Daily ad-level insights |
| `raw_ga4` | Raw (optional) | Sessions by source |

## Settings (named ranges)

`target_contribution_margin`, `min_cash_reserve`, `payment_fee_pct`, `cod_fee_pct`, `cod_share`, `cod_failed_rate`, `shipping_subsidy_per_order`, `fulfillment_per_order`, `allowable_cac_share` (share of pre-ad contribution you are willing to spend on acquisition), `safety_stock_days`, `fx_egp_usd` (label the date), `ad_attribution_window`.

## Products (key columns)

`sku · name · drop_id · category · color · size_run · supplier_id · fabric · sample_status · production_status · moq · qty · factory_cost · fabric_cost · packaging_cost · freight_per_unit · customs_duties_per_unit · other_direct_per_unit · landed_cost · price · discount_pct · net_price · gross_margin_pct · cm_per_order_pre_ads · allowable_cac · launch_date · units_sold · units_remaining`

```
landed_cost          = SUM(factory_cost:other_direct_per_unit)
net_price            = price * (1 - discount_pct)
variable_cost_order  = payment_fee_pct*net_price + shipping_subsidy + fulfillment + expected_return_cost
cm_per_order_pre_ads = net_price - landed_cost - variable_cost_order
allowable_cac        = cm_per_order_pre_ads * allowable_cac_share
```

Adjust for COD: expected failed-delivery cost = `cod_share * cod_failed_rate * (outbound + return shipping)`. This number comes from the founder's carrier data, not a benchmark.

## Drops (master drop tracker)

| drop · product · status · qty · unit_cost · selling_price · revenue · margin · sold · remaining · CAC · contribution_profit · next_action |
|---|

Formulas (per drop `D`):

```
revenue             = SUMIFS(raw_shopify_orders!net_sales, drop_id, D)
units_sold          = SUMIFS(raw_shopify_orders!qty, drop_id, D)
remaining           = SUMIFS(Products!qty, drop_id, D) - units_sold - returns_damaged_gifted
sell_through        = units_sold / SUMIFS(Products!qty, drop_id, D)
drop_investment     = samples + pattern + production + packaging + campaign + shoot + creators + paid_media + website + logistics
contribution_profit = net_revenue - COGS_sold - variable_costs - paid_media
cash_generated      = cash_in - cash_out_for_drop
```

Each drop has its own mini P&L block. Adding a drop = adding rows; no formula edits.

## Production

Stage list: Concept → Design → Fabric sourcing → Sample → Fitting → Revision → Final sample → Costing → Production decision → Deposit → Production → QA → Delivery → Inventory → Launch → Sell-through → Reorder/End.

Columns per stage row: `sku · stage · start · end · cost · notes · attachment_link · decision · supplier_comms · problem · next_action`.

Lead-time dates: `deposit · prod_start · prod_end · qa · cargo_ready · shipped · customs · warehouse · available`. `lead_time_days = available − deposit`; roll up the average per supplier and feed it to the reorder point.

QC: `units_total · units_defective · units_altered · units_rejected · defect_rate`.

## Inventory

```
daily_velocity     = units_sold_last_14d / 14   (state the window; 28d for slow SKUs)
days_of_inventory  = on_hand / daily_velocity
reorder_point      = daily_velocity * lead_time_days + safety_stock_days * daily_velocity
stockout_date      = TODAY() + days_of_inventory
reorder_flag       = on_hand <= reorder_point AND cash_ok AND cm_per_order_pre_ads > 0
```

Size/color-level inventory matters for fashion: a SKU can be "in stock" while its best-selling size is out. Track velocity per variant.

## Content

`content_id · idea · objective · funnel_stage · category · format · hook · script_link · shoot_date · edit_date · publish_date · platform · production_cost · organic_reach · organic_engagement · saves · shares · profile_visits · link_clicks · paid_test (Y/N) · campaign_id · paid_spend · paid_cpa · attributed_revenue · learning`

## Campaigns and Creative Tests

`campaign_id · drop_id · objective · funnel_stage · start · end · budget · spend · impressions · clicks · purchases · revenue · CTR · CPC · CPM · CVR · CAC · ROAS · MER_contribution · decision`

`creative_id · content_id · concept · hook · format · creator · first_live · spend · frequency · CTR_d1 · CTR_now · CPM_d1 · CPM_now · CPA_now · status (testing/scaling/fatigued/retired) · learning`

## Cash

Weekly rows. Inflows: Shopify payouts (by actual payout date), COD remittance (carrier lag, state it), other. Outflows: deposits, balance payments, ad spend (platform billing date), content, freelancers, software, debt.

```
closing_cash   = opening + inflows - outflows
deployable     = closing - min_cash_reserve - committed_next_30d
runway_months  = deployable / avg_monthly_net_burn
```

Show **7 / 30 / 90-day** views. COD cash lag is a first-class variable for Egypt.

## Dashboard

Sections: Cash · Sales · Marketing · Inventory · Production · Content · CEO Actions (DECIDE / FIX / TEST / WAIT / INVESTIGATE). Mockup in `dashboard-mockups.md`.

## Editing Rules (for agents)

1. Change inputs only in input tabs; log the change in `Decision_Log` if it affects a decision.
2. Never overwrite a formula with a value.
3. Never hand-edit `raw_*` tabs.
4. Before writing, state the range, the old value and the new value; write after approval.
5. After writing, recalculate and report which downstream numbers moved.
