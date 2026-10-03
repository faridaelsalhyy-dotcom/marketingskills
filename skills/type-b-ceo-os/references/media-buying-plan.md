# Media Buying Strategy and Plan

Think like a media buyer, decide like a CEO: every ad decision is tested against **allowable CAC**, stock and cash.

## Step 0: Know the Constraints Before Spending

```
cm_per_order_pre_ads (from Products tab)
allowable_cac = cm_per_order_pre_ads × allowable_cac_share
breakeven_ROAS = AOV ÷ cm_per_order_pre_ads          (platform ROAS needed to cover ads at 0 profit)
```

If `allowable_cac` is tiny or negative, **do not buy media**. Fix price, cost, offer, bundle or conversion first. Report that to the founder as the real decision.

## Funnel Structure (start simple)

| Layer | Meta structure at NOW stage | Purpose |
|-------|------------------------------|---------|
| **Testing** | 1 campaign, ABO or CBO with equal-ish ad-set budgets; 1 broad audience ad set per concept cluster | Find winning hooks/concepts cheaply |
| **Scaling** | 1 campaign with proven creatives, broad (Advantage+ audience / Advantage+ sales campaign where the account supports it) | Spend on winners |
| **Retargeting** | 1 campaign: site visitors / engagers / ATC / checkout, excluding purchasers | Capture existing intent |
| **Retention** | Past-buyer lists | Next drop, cross-sell |

Do not over-segment. Small budgets starve the algorithm. Verify the current Meta campaign options in Ads Manager docs before building; names and defaults change.

## Naming Convention

`{drop}_{objective}_{funnel}_{audience}_{date}` for campaign/ad set; ads: `{content_id}_{hook}_{format}_{version}`
Example: `D1_SALES_TEST_BROAD_2026-11` · `C-0042_confession_reel_v2`

## Budget Plan Template (every number is an ASSUMPTION until she supplies it)

| Line | Share | Notes |
|------|------:|-------|
| Testing | 30–40% | New creative discovery; higher early share, shrinks as winners appear |
| Scaling | 40–50% | Proven creatives |
| Retargeting | 10–15% | Scale with traffic |
| Reserve | 5–10% | Opportunities/pivot |

```
total_drop_media_budget ≤ min( deployable_cash_for_ads , max_spend_justified_by_stock )
max_spend_justified_by_stock = units_available × sell-through_target × allowable_cac
```

This stock cap prevents buying demand for product that does not exist.

## Testing Protocol

1. **Hypothesis per test:** e.g. "Recognition hooks beat product-first hooks on 3-s hold and CPA."
2. **One variable per test** (hook, format, voice, or offer), others held constant.
3. **Spend a minimum before judging:** a rule-of-thumb floor is ~1–2× allowable CAC per ad before a "no-purchase" kill, adjusted to real CPMs and volume. State it as a rule of thumb, not a statistical guarantee.
4. Read in this order: **hook rate** (3-s views ÷ impressions) → **hold rate** → **CTR (link)** → **CPC** → **LP view rate** → **ATC rate** → **checkout rate** → **purchase rate/CPA**. The first broken step tells you where to fix.
5. Log verdicts in `Creative_Tests` with learning, not just win/lose.

## Diagnostic Table

| Symptom | Likely layer | First action |
|---------|--------------|--------------|
| High CPM, normal CTR | Audience/auction/season | Check payday/event competition; broaden audience |
| Low hook rate | Creative opening | New first 3 seconds |
| Good CTR, low LP view rate | Click quality/site speed | Check mobile speed, in-app browser, tracking |
| Good LP views, low ATC | Product page/price/size | Fix PDP: size guide, price framing, proof |
| High ATC, low checkout | Shipping/COD/payment friction | Clarify COD, payment options, delivery time |
| Good Meta ROAS, weak Shopify | Attribution over-claim / tracking | Compare MER, new-customer rate; check CAPI dedup |
| Rising CPA, rising frequency, falling CTR | Fatigue | New concept (not just copy) |

## Scale / Hold / Kill Rules (starting framework; tune with account data)

- **Scale** a winner when CAC ≤ allowable CAC for ≥ 3–5 days *with sufficient purchase volume*, stock covers the extra spend, and cash covers the float. Increase budgets in measured steps (a common practice is ~20% per step with a pause for the algorithm to settle; verify against current Meta behavior) rather than doubling overnight.
- **Hold** when CAC is within ~20% of allowable and volume is thin; wait for more data.
- **Kill** when spend ≥ the testing floor with weak leading indicators and no purchases, or CAC is well above allowable over a meaningful window **and** a diagnostic shows no fixable upstream cause.
- **Do not kill** on one day of data, or when the issue is the LP/offer rather than the ad.
- **Cap** scale when projected sell-through reaches the stock limit; shift to retargeting and next-drop teasing.

## Measurement Stack

| Question | Source |
|----------|--------|
| Did we make money? | Shopify net sales − costs (Master Sheet) |
| Is paid efficient? | CAC vs allowable CAC; MER |
| Which ad is working? | Meta ad-level insights (directional) |
| Are platforms over-claiming? | Meta purchases vs Shopify orders with `utm_*` / new-customer flag |
| Is growth incremental? | Holdout/geo/time-based tests at NEXT/SCALE stage; MMM only with enough data |

Attribution views will differ (platform window, view-through, last-click in Shopify). Always state which window and view each figure uses.

## Weekly Media Review (30 min)

1. MER and blended CAC vs allowable → on track?
2. Funnel diagnostic: where is the leak?
3. Creative portfolio: winners / fatigue / next tests (set 3 launches for next week)
4. Budget moves: with stock and cash check
5. Log decisions and learning; update `Campaigns` and `Creative_Tests`

## Media Plan Output (what you deliver to the founder)

1. Constraint block: allowable CAC, breakeven ROAS, stock cap, cash cap
2. Budget table by layer and week (Conservative/Base/Upside)
3. Creative testing calendar (concept × hook × format × week)
4. Tracking readiness checklist
5. Decision rules and review dates
6. "Change my mind if…" triggers

Example week table:

| Week | Phase | Budget | Layer focus | Creative launched | Decision checkpoint |
|------|-------|-------:|-------------|-------------------|---------------------|
| T-3 | Tease | (assumption) | Lead gen test | 3 hooks | Pick top 2 by cost per lead |
| T-1 | Pre-launch | | Testing | 6 variants | Select launch creatives |
| T0–T+1 | Launch | | Test + scale | winners + 2 new | Day-1, Day-3 CAC read |
| T+2–T+7 | Launch | | Scale + retarget | 2 new/wk | Stock cap check |
| T+8+ | Sustain | | Retarget + winners | refreshed | Retro T+14 |

## Egypt Notes (verify with her own data before using)

COD share, failed-delivery/refusal rate, payment mix, mobile-first browsing, local CPMs and payday timing all change the math. Treat any benchmark as **unverified** until sourced and dated, and prefer her own account data after the first 2–4 weeks.
