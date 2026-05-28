---
template: stage5-verification
purpose: "Manual recomputation of selected ratios from Stage 3 source data, cross-checked against the LLM raw output values"
audience: Stage 5 grader; sceptical reviewer of LLM numerical work
stage: 5
author: Hai Dang (VEMBA)
date: 2026-05-27
company: AB SKF
ticker: SKFB.ST
sources:
  - models/builds/2026-05-19-dang-skf-financials.xlsx (Stage 3 audited model)
  - docs/specs/2026-05-24-dang-skf-spec.md v2.0 (formulas, named ranges)
  - deliverables/2026-05-27-dang-skf-llm-raw.md (LLM raw output under test)
---

# Stage 5 Manual Verification Table — AB SKF FY2025

**Purpose.** Recompute selected ratios by hand from the Stage 3 audited source data and compare against the values quoted in the Stage 5 LLM raw output. This is the verification discipline checkpoint required by Stage 5 rubric (10% weight). Discrepancies are not failures if explained; unexplained discrepancies earn no credit.

**Selection rationale.** I selected ratios biased toward known LLM failure modes — those involving (i) start-of-year denominators that are easily confused with current-year, (ii) unit conversions (e.g., daily COGS, share-count scaling), and (iii) chained rounding (Du Pont). Nine ratios are checked across all six categories.

**Source values used (all from Stage 3 workbook, FY2025 unless noted):**

| Input | Value | Source |
|-------|------:|--------|
| `INC_sales` | 91,583 | IS tab |
| `INC_cost_goods_sold` | 62,434 | IS tab |
| `INC_ebit` | 7,498 | IS tab (derived) |
| `INC_interest_expense` | 1,330 | IS tab |
| `INC_net` | 4,249 | IS tab |
| `BAL_assets_total_curr` | 106,422 | BS tab |
| `BAL_assets_total_prior` | 119,413 | BS tab |
| `BAL_equity_shareholders_curr` | 55,668 | BS tab |
| `BAL_equity_shareholders_prior` | 61,969 | BS tab |
| `BAL_inventories_prior` | 26,182 | BS tab |
| `BAL_debt_long_term_prior` | 15,399 | BS tab |
| `BAL_assets_current_curr` | 54,331 | BS tab |
| `BAL_liabilities_current_curr` | 25,757 | BS tab |
| `tax_rate` | 33.86% | Ratios tab assumption |
| `cost_capital` | 9.00% | Ratios tab assumption |
| `share_price` | SEK 245.80 | Ratios tab assumption |
| `shares_outstanding` | 455.35 (millions) | Ratios tab assumption |

**Derived:**
- `currentYear_after_tax_operating_income` = 4,249 + (1 − 0.3386) × 1,330 = **5,128.66**
- `startYear_total_capitalization` = 15,399 + 61,969 = **77,368**

---

## Verification Table

| # | Ratio | Category | Formula (named-range) | Manual recomputation | LLM value | Match | Note |
|---|-------|----------|----------------------|---------------------|----------:|:-----:|------|
| **R1** | **EVA** | Performance | `currentYear_after_tax_operating_income − (cost_capital × startYear_total_capitalization)` | 5,128.66 − (0.09 × 77,368) = 5,128.66 − 6,963.12 = **−1,834.46 MSEK** | (1,835) | ✓ within rounding | LLM rounds ATOI to 5,128 → EVA = (1,835). My precise calc using ATOI = 5,128.66 gives (1,834.46). Difference of 0.5 MSEK is rounding chain in the ATOI step. **Sign and economic interpretation identical**. |
| **R2** | **ROE (direct)** | Profitability | `INC_net / startYear_equity` | 4,249 / 61,969 = 0.068566 = **6.86%** | 6.86% | ✓ | Matches precisely. The critical test is denominator choice — using `startYear_equity` (FY2024 = 61,969) per spec convention, not `currentYear_equity` (55,668), which would give 4,249 / 55,668 = 7.63% (a typical LLM mistake when the convention is not pinned down). LLM correctly used start-of-year. |
| **R3** | **Asset turnover** | Efficiency | `INC_sales / startYear_total_assets` | 91,583 / 119,413 = 0.76695 = **0.77x** | 0.77x | ✓ | Matches at 2-decimal precision. Same denominator convention test as R2: using current-year (106,422) would give 0.86x, a 12% inflation. LLM correctly used start-of-year. |
| **R4** | **Inventory turnover** | Efficiency | `INC_cost_goods_sold / startYear_inventory` | 62,434 / 26,182 = 2.38453 = **2.38x** | 2.38x | ✓ | Matches. Uses prior-year inventory denominator per spec — a CFA-style calc using average inventory `(26,182 + 23,677) / 2 = 24,930` would give 2.50x. LLM correctly followed spec convention. |
| **R5** | **Days in inventory** | Efficiency | `startYear_inventory / currentYear_cost_goods_sold_daily` where `currentYear_cost_goods_sold_daily = INC_cost_goods_sold / 365` | Daily COGS = 62,434 / 365 = 171.052. Days = 26,182 / 171.052 = **153.09 = 153.1 days** | 153.1 | ✓ | Matches. Two-step calc with daily-COGS intermediate (unit conversion) executed correctly. A common LLM error: using sales-daily instead of COGS-daily → 26,182 / 250.91 = 104.3 days (wrong). LLM avoided this error. |
| **R6** | **Times interest earned** | Leverage | `INC_ebit / INC_interest_expense` | 7,498 / 1,330 = 5.6376 = **5.64x** | 5.64x | ✓ | Matches. Straightforward IS-to-IS calc. Note: EBIT is a derived value (Sales − COGS − SG&A − D&A = 91,583 − 62,434 − 17,027 − 4,624 = 7,498) and is correctly used; LLM did not mistakenly substitute Operating Profit reported (different concept). |
| **R7** | **Current ratio** | Liquidity | `currentYear_assets_current / currentYear_liabilities_current` | 54,331 / 25,757 = 2.1094 = **2.11x** | 2.11x | ✓ | Matches. Uses current-year balances per liquidity-ratio convention (snapshot, not flow). |
| **R8** | **Du Pont ROE** | Du Pont | `RATIO_leverage × RATIO_asset_turnover × RATIO_operating_profit_margin × RATIO_debt_burden` | Full precision: 1.91136 × 0.76695 × 0.05601 × 0.82850 = **6.802% = 6.80%**. Rounded-chain: 1.91 × 0.77 × 0.0560 × 0.829 = 6.827% = 6.83%. | 6.83% (rounded chain) and 6.80% (per spec) — both reported | ✗→✓ minor | LLM reported BOTH 6.83% (its rounded-chain answer) AND 6.80% (the spec value). The **correct figure is 6.80%**; the 6.83% is an arithmetic artefact of rounding each driver to 2-3 sig figs before chaining. This is the classic "fake precision" LLM trap. **Correction for Final Analysis: cite only 6.80%, suppress 6.83%.** V9 reconciliation to direct ROE 6.86% (6 bps gap = denominator timing) holds against 6.80% but would mislead against 6.83%. |
| **R9** | **Market capitalization** | Performance (input) | `share_price × shares_outstanding × 1000` (spec formula) | Spec formula: 245.80 × 455.35 × 1000 = 111,925,030 (not 111,925 as spec result shows). Correct unit reasoning: SEK × millions of shares = MSEK directly, so `share_price × shares_outstanding` (no ×1000) = 245.80 × 455.35 = **111,925.03 MSEK** | 111,925 | ✓ (result) / ✗ (formula notation) | LLM result correct, **but spec formula notation defective**: the "× 1000" multiplier is inconsistent with shares stated in millions. Either (a) drop the "× 1000" and state shares in M, or (b) keep "× 1000" and state shares in billions (= 0.45535). This is a **Stage 4 spec defect** to flag in the spec retrospective, not an LLM error. |

---

## Summary

| Bucket | Count |
|--------|------:|
| Ratios verified | 9 |
| Exact matches | 7 |
| Match within rounding | 1 (R1 EVA, 0.5 MSEK rounding-chain difference) |
| Discrepancy requiring correction | 1 (R8 Du Pont ROE — LLM's 6.83% should be suppressed; 6.80% retained) |
| Spec defects flagged | 1 (R9 market-cap formula notation) |

**Discrepancies explained:**

- **R1 (EVA −1,834.46 vs LLM −1,835)**: Rounding chain. Spec rounds ATOI to integer MSEK (5,128) before applying capital charge; my precise calc carries 0.66 MSEK through. The 0.5 MSEK swing does not change sign, magnitude, or interpretation. **Final Analysis cites −1,835** (matches spec convention and LLM) with a footnote acknowledging the 0.5 MSEK rounding-chain artefact.

- **R8 (Du Pont ROE 6.80% precise vs 6.83% rounded)**: The LLM transparently reported both values and labelled the difference. This is the right behaviour — but the Final Analysis should pick one and stick with it. **I retain 6.80%** because (i) it matches the spec, (ii) the chained-rounding error is the documented Stage-4-known issue (V9), and (iii) the 6 bps reconciliation to direct ROE 6.86% only holds against 6.80%.

- **R9 (Market cap formula notation)**: Stage 4 spec defect (§5 formula uses "× 1000" inconsistent with shares-in-millions input). The output value 111,925 MSEK is correct; the formula notation is misleading. Flagged in the Spec Retrospective (gap analysis) — would be a Round 3 fix if I were re-iterating the spec.

---

## What the verification adds beyond LLM execution

1. **Convention testing**: R2, R3, R4 all probe the start-of-year vs current-year denominator convention. The LLM passed all three — the spec's explicit `startYear_*` named-range convention was strong enough to prevent the most common LLM error in ratio analysis.

2. **Unit-conversion testing**: R5 (days in inventory, daily-COGS) and R9 (market cap, share-scaling) probe places where unit confusion is easy. The LLM passed R5 cleanly; R9 surfaced a spec-notation defect, not an LLM error.

3. **Chained-rounding test**: R8 caught the only LLM computational discrepancy — and the LLM had already flagged it transparently, demonstrating that disciplined prompting (the spec's V9 explicit reconciliation rule) extracts higher-quality LLM behaviour than asking for a single number.

4. **No verification step is a substitute for understanding the convention**: every ✓ in the table required me to know what denominator and what unit the spec intended. The verification table is the discipline checkpoint the spec rubric requires — the LLM is a tool, not an oracle.

---

*End of verification artefact. Corrections noted here flow into `deliverables/2026-05-27-dang-skf-final-analysis.md`. Spec defects flow into `deliverables/2026-05-27-dang-skf-spec-retrospective.md`.*
