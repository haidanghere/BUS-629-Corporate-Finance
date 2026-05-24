---
template: spec-template
purpose: Define the Excel ratio model and analytical work for Stage 5 execution
audience: LLM executing Stage 5 analysis (no prior context assumed)
stage: 4
author: Hai Dang (VEMBA)
company: AB SKF
ticker: SKFB.ST
date: 2026-05-24
revised: 2026-05-24  # v2 — added §6g, §8b, §8c, V7-V9, §12 sensitivity, named-range col in §3, revision log; trimmed to target word band
model_file: models/builds/2026-05-19-dang-skf-financials.xlsx
fiscal_year_current: FY2025 (Jan 1 – Dec 31, 2025)
reporting_standard: IFRS (as adopted by the EU; audited by PwC)
currency: MSEK
---

# Technical Specification — AB SKF Accounting & Performance Ratios
**BUS-629 VEMBA · Stage 4 · Hai Dang**

---

## PART A — MODEL SPECIFICATION

### 1. Scope & Objective

Quantify AB SKF FY2025 performance via the 30-ratio framework; decompose ROE via Du Pont; deliver 3–5 CFO-grade recommendations in context of FY2025 Automotive divestiture.

- **Subject:** AB SKF (publ.); SKFB B-share, Nasdaq Stockholm; GICS 20305010
- **Period:** Current = FY2025; Prior = FY2024
- **Standard:** IFRS (EU); audited PwC; source = AB SKF AR2025
- **Currency:** MSEK; **Audience:** SKF CFO & exec committee

Model is read-only at Stage 5.

---

### 2. Model Architecture

Workbook `2026-05-19-dang-skf-financials.xlsx`, 6 tabs:

| Tab | Role |
|-----|------|
| Cover | Metadata, version |
| Balance Sheet | FY2025 + FY2024 side-by-side |
| Income Statement | FY2025 P&L + `% of Sales` |
| Cash Flow Statement | FY2025 indirect (Ops/Inv/Fin) |
| Ratios | Assumptions → Derived → 30 ratios |
| Notes | Sources, AI usage, self-checks |

Color: Blue = inputs; Black = formulas; Green = cross-sheet links; Yellow fill = assumptions. Format: `$#,##0`; 0.0%; 0.0x; zeros `-`; negatives `(123)`; Open Sans.

---

### 3. Data Inputs — Numerical Values

MSEK; source AR2025.

#### 3a. Income Statement (FY2025)

| Named Range | Line Item | FY2025 |
|-------------|-----------|-------:|
| `INC_sales` | Net sales | 91,583 |
| `INC_cost_goods_sold` | Cost of goods sold | 62,434 |
| `INC_sga` | SG&A | 17,027 |
| `INC_depreciation` | Depreciation | 4,624 |
| `INC_ebit` | EBIT (formula) | 7,498 |
| `INC_other_income` | Other income | 257 |
| `INC_interest_expense` | Interest expense | 1,330 |
| `INC_taxable_income` | Taxable income (formula) | 6,425 |
| `INC_taxes` | Taxes | 2,176 |
| `INC_net` | Net income (formula) | 4,249 |
| `INC_dividends` | Dividends | 3,529 |
| `INC_addition_retained_earnings` | Addition to RE (formula) | 720 |

#### 3b. Balance Sheet — Current (FY2025)

| Named Range | Line Item | FY2025 |
|-------------|-----------|-------:|
| `BAL_cash_marketable_securities_curr` | Cash & marketable securities | 8,984 |
| `BAL_receivables_curr` | Receivables | 15,408 |
| `BAL_inventories_curr` | Inventories | 23,677 |
| `BAL_other_current_assets_curr` | Other current assets | 6,262 |
| `BAL_assets_current_curr` | Total current assets | 54,331 |
| `BAL_ppe_gross_curr` | PP&E gross | 66,041 |
| `BAL_accumulated_depreciation_curr` | Accumulated depreciation | 38,256 |
| `BAL_fixed_assets_net_curr` | Net PP&E | 27,785 |
| `BAL_intangibles_curr` | Goodwill & intangibles | 14,412 |
| `BAL_other_assets_curr` | Other assets | 9,894 |
| `BAL_assets_total_curr` | Total Assets | 106,422 |
| `BAL_debt_short_term_curr` | Short-term debt | 1,172 |
| `BAL_accounts_payable_curr` | Accounts payable | 11,207 |
| `BAL_other_current_liabilities_curr` | Other current liabilities | 13,378 |
| `BAL_liabilities_current_curr` | Total current liabilities | 25,757 |
| `BAL_debt_long_term_curr` | Long-term debt | 14,168 |
| `BAL_other_long_term_liabilities_curr` | Other long-term liabilities | 10,829 |
| `BAL_liabilities_total_curr` | Total liabilities | 50,754 |
| `BAL_common_stock_curr` | Common stock & paid-in capital | 1,702 |
| `BAL_retained_earnings_curr` | Retained earnings | 53,966 |
| `BAL_equity_shareholders_curr` | Total shareholders' equity | 55,668 |

#### 3c. Balance Sheet — Prior (FY2024) — `startYear_*` inputs

| Named Range | Line Item | FY2024 |
|-------------|-----------|-------:|
| `BAL_cash_marketable_securities_prior` | Cash & marketable securities | 11,031 |
| `BAL_receivables_prior` | Receivables | 16,600 |
| `BAL_inventories_prior` | Inventories | 26,182 |
| `BAL_other_current_assets_prior` | Other current assets | 6,387 |
| `BAL_assets_current_prior` | Total current assets | 60,200 |
| `BAL_ppe_gross_prior` | PP&E gross | 71,970 |
| `BAL_accumulated_depreciation_prior` | Accumulated depreciation | 41,500 |
| `BAL_fixed_assets_net_prior` | Net PP&E | 30,470 |
| `BAL_intangibles_prior` | Goodwill & intangibles | 17,245 |
| `BAL_other_assets_prior` | Other assets | 11,498 |
| `BAL_assets_total_prior` | Total Assets | 119,413 |
| `BAL_debt_short_term_prior` | Short-term debt | 5,361 |
| `BAL_accounts_payable_prior` | Accounts payable | 12,553 |
| `BAL_other_current_liabilities_prior` | Other current liabilities | 12,220 |
| `BAL_liabilities_current_prior` | Total current liabilities | 30,134 |
| `BAL_debt_long_term_prior` | Long-term debt | 15,399 |
| `BAL_other_long_term_liabilities_prior` | Other long-term liabilities | 11,911 |
| `BAL_liabilities_total_prior` | Total liabilities | 57,444 |
| `BAL_common_stock_prior` | Common stock & paid-in capital | 1,702 |
| `BAL_retained_earnings_prior` | Retained earnings | 60,267 |
| `BAL_equity_shareholders_prior` | Total shareholders' equity | 61,969 |

#### 3d. Cash Flow Statement (FY2025)

| Named Range | Line Item | FY2025 |
|-------------|-----------|-------:|
| `CASH_operating` | Cash from Operations | 7,978 |
| `CASH_investments` | Cash from Investing | (1,500) |
| `CASH_financing` | Cash from Financing | (8,289) |
| `CASH_net_change` | Net change in cash | (1,811) |

> Template (1,811) vs AR2025 (2,047): 236 MSEK gap = non-cash items + FX translation ~650 MSEK. Not an error.

#### 3e. Analyst Assumptions

| Named Range | Input | Value |
|-------------|-------|------:|
| `yearCurrent` | Fiscal year (current) | 2025 |
| `share_price` | SKFB B-share close, Dec 31 2025 | SEK 245.80 |
| `shares_outstanding` | Basic = diluted (M) | 455.35 |
| `cost_capital` | Class default | 9.00% |
| `tax_rate` | Effective rate FY2025 | 33.86% |

---

### 4. Named Range Conventions

| Prefix | Scope | Example |
|--------|-------|---------|
| `BAL_[item]_curr` | Balance sheet, current year | `BAL_assets_total_curr` |
| `BAL_[item]_prior` | Balance sheet, prior year | `BAL_assets_total_prior` |
| `INC_[item]` | Income statement | `INC_sales`, `INC_net` |
| `CASH_[item]` | Cash flow | `CASH_operating` |
| `startYear_[item]` | Alias → `BAL_[item]_prior` | `startYear_equity` |
| `currentYear_[item]` | Alias or derived | `currentYear_equity` |
| `avg_[item]` | `(start + current) / 2` | `avg_equity` |
| `RATIO_[name]` | Reused in Du Pont | `RATIO_leverage` |

No direct cell references in any ratio formula.

---

### 5. Derived Inputs

| Named Range | Formula | Value |
|-------------|---------|------:|
| `yearStart` | `yearCurrent − 1` | 2024 |
| `market_capitalization` | `share_price × shares_outstanding × 1000` | 111,925 |
| `startYear_equity` | `BAL_equity_shareholders_prior` | 61,969 |
| `startYear_inventory` | `BAL_inventories_prior` | 26,182 |
| `startYear_receivables` | `BAL_receivables_prior` | 16,600 |
| `startYear_total_assets` | `BAL_assets_total_prior` | 119,413 |
| `startYear_total_capitalization` | `BAL_debt_long_term_prior + BAL_equity_shareholders_prior` | 77,368 |
| `currentYear_equity` | `BAL_equity_shareholders_curr` | 55,668 |
| `currentYear_cash_marketable_securities` | `BAL_cash_marketable_securities_curr` | 8,984 |
| `currentYear_assets_current` | `BAL_assets_current_curr` | 54,331 |
| `currentYear_liabilities_current` | `BAL_liabilities_current_curr` | 25,757 |
| `currentYear_debt_long_term` | `BAL_debt_long_term_curr` | 14,168 |
| `currentYear_assets_total` | `BAL_assets_total_curr` | 106,422 |
| `currentYear_liabilities_total` | `BAL_liabilities_total_curr` | 50,754 |
| `currentYear_total_capitalization` | `currentYear_debt_long_term + currentYear_equity` | 69,836 |
| `currentYear_working_capital_net` | `currentYear_assets_current − currentYear_liabilities_current` | 28,574 |
| `currentYear_after_tax_operating_income` | `INC_net + (1 − tax_rate) × INC_interest_expense` | 5,128 |
| `currentYear_daily_sales_average` | `INC_sales / 365` | 250.91 |
| `currentYear_cost_goods_sold_daily` | `INC_cost_goods_sold / 365` | 171.05 |
| `avg_equity` | `AVERAGE(startYear_equity, currentYear_equity)` | 58,818.5 |
| `avg_total_assets` | `AVERAGE(startYear_total_assets, currentYear_assets_total)` | 112,917.5 |
| `avg_total_capitalization` | `AVERAGE(startYear_total_capitalization, currentYear_total_capitalization)` | 73,602 |

---

### 6. Ratio Definitions & Formulas

**30 ratios** across 6 categories.

#### 6a. Performance

| Metric | Formula | FY2025 |
|--------|---------|-------:|
| MVA | `market_capitalization − currentYear_equity` | 56,257 |
| Market-to-Book | `market_capitalization / currentYear_equity` | 2.01x |
| **EVA** | `currentYear_after_tax_operating_income − (cost_capital × startYear_total_capitalization)` | **(1,835)** |

#### 6b. Profitability

| Metric | Formula | FY2025 |
|--------|---------|-------:|
| ROA | `currentYear_after_tax_operating_income / startYear_total_assets` | 4.29% |
| ROC | `currentYear_after_tax_operating_income / startYear_total_capitalization` | 6.63% |
| ROE | `INC_net / startYear_equity` | 6.86% |
| ROA [avg] | `currentYear_after_tax_operating_income / avg_total_assets` | 4.54% |
| ROC [avg] | `currentYear_after_tax_operating_income / avg_total_capitalization` | 6.97% |
| ROE [avg] | `INC_net / avg_equity` | 7.22% |

#### 6c. Efficiency

| Metric | Named Range | Formula | FY2025 |
|--------|-------------|---------|-------:|
| Asset turnover | `RATIO_asset_turnover` | `INC_sales / startYear_total_assets` | 0.77x |
| Receivables turnover | — | `INC_sales / startYear_receivables` | 5.52x |
| Avg collection period | — | `startYear_receivables / currentYear_daily_sales_average` | 66.2 days |
| Inventory turnover | — | `INC_cost_goods_sold / startYear_inventory` | 2.38x |
| Days in inventory | — | `startYear_inventory / currentYear_cost_goods_sold_daily` | 153.1 days |
| Profit margin | — | `INC_net / INC_sales` | 4.64% |
| Operating profit margin | `RATIO_operating_profit_margin` | `currentYear_after_tax_operating_income / INC_sales` | 5.60% |

#### 6d. Leverage

| Metric | Named Range | Formula | FY2025 |
|--------|-------------|---------|-------:|
| LT debt ratio | — | `currentYear_debt_long_term / (currentYear_debt_long_term + currentYear_equity)` | 20.3% |
| LT debt-to-equity | — | `currentYear_debt_long_term / currentYear_equity` | 25.5% |
| Total debt ratio | — | `currentYear_liabilities_total / currentYear_assets_total` | 47.7% |
| Times interest earned | — | `INC_ebit / INC_interest_expense` | 5.64x |
| Cash coverage | — | `(INC_ebit + INC_depreciation) / INC_interest_expense` | 9.11x |
| Debt burden | `RATIO_debt_burden` | `INC_net / currentYear_after_tax_operating_income` | 0.829 |
| Leverage ratio | `RATIO_leverage` | `currentYear_assets_total / currentYear_equity` | 1.91x |

#### 6e. Liquidity

| Metric | Formula | FY2025 |
|--------|---------|-------:|
| NWC to Assets | `currentYear_working_capital_net / currentYear_assets_total` | 26.8% |
| Current ratio | `currentYear_assets_current / currentYear_liabilities_current` | 2.11x |
| Quick ratio | `(currentYear_cash_marketable_securities + BAL_receivables_curr) / currentYear_liabilities_current` | 0.95x |
| Cash ratio | `currentYear_cash_marketable_securities / currentYear_liabilities_current` | 0.35x |

#### 6f. Du Pont System

| Metric | Formula | FY2025 |
|--------|---------|-------:|
| ROA (Du Pont) | `RATIO_asset_turnover × RATIO_operating_profit_margin` | 4.29% |
| ROE (Du Pont) | `RATIO_leverage × RATIO_asset_turnover × RATIO_operating_profit_margin × RATIO_debt_burden` | 6.80% |

> Du Pont ROE (6.80%) ≠ direct ROE (6.86%): leverage uses current-year, turnover uses prior-year. Explain as structural, not error.

#### 6g. Interpretation Guide

| Category | High | Low | **SKF FY2025** |
|----------|------|-----|----------------|
| Performance | EVA > 0 | EVA < 0 | **LOW** — EVA (1,835) |
| Profitability | ROE > 15%, margin > 10% | ROE < 10%, margin < 7% | **LOW** — ROE 6.86%, op margin 5.60% |
| Efficiency | Inventory < 90 days | Inventory > 120 days | **MIXED** — receivables 66 OK; inventory 153 = drag |
| Leverage | TIE > 5x, debt < 50% | TIE < 3x, debt > 70% | **HEALTHY** — TIE 5.64x, debt 47.7% |
| Liquidity | Current > 1.5x | Current < 1.2x | **STRONG** — Current 2.11x |
| Du Pont | Balanced drivers | One weak driver | **MARGIN-LIMITED** — 5.60% binding |

---

### 7. Validation Rules

| # | Check | Pass condition |
|---|-------|---------------|
| V1 | BS balance FY2025 | `BAL_assets_total_curr` = `BAL_liabilities_total_curr + BAL_equity_shareholders_curr` → 106,422 ✓ |
| V2 | BS balance FY2024 | `BAL_assets_total_prior` = `BAL_liabilities_total_prior + BAL_equity_shareholders_prior` → 119,413 ✓ |
| V3 | IS arithmetic | `INC_ebit` = `INC_sales − INC_cost_goods_sold − INC_sga − INC_depreciation` → 7,498 ✓ |
| V4 | Net income | `INC_net` = `INC_taxable_income − INC_taxes` → 4,249 ✓ |
| V5 | Du Pont ROA match | `RATIO_asset_turnover × RATIO_operating_profit_margin` ≈ direct ROA → 4.29% ✓ |
| V6 | No formula errors | Zero `#REF!`, `#DIV/0!`, `#NAME?` on Ratios tab |
| V7 | EVA sign | EVA < 0 expected; confirms ROC (6.63%) < WACC (9.0%) → (1,835) ✓ |
| V8 | Positive startYear | `startYear_equity`, `startYear_total_assets`, `startYear_total_capitalization` > 0 ✓ |
| V9 | Du Pont ROE reconciliation | Du Pont ROE positive; 6 bps gap vs direct acknowledged as denominator mismatch ✓ |

---

## PART B — ANALYSIS SPECIFICATION

### 8a. Analysis Requirements

For each of 5 categories (Performance / Profitability / Efficiency / Leverage / Liquidity): 2–3 sentences with ratio value, interpretation, YoY change.

Cross-category required: profit↔efficiency (low ROA from margin, not turnover); profit↔performance (ROC < WACC → negative EVA); leverage↔profit (debt burden 0.829 = interest drag); Automotive divestiture FY2026 ROCE impact.

Benchmarks: (1) SKF FY2024 YoY; (2) Peers — Schaeffler, NSK, NTN, Timken; (3) ROCE target 14%; (4) WACC 9.0%.

### 8b. Hypothesis Evaluation (from Stage 2)

Verdict **CONFIRMED / REJECTED / INCONCLUSIVE** + 2–3 sentence justification citing ratio values.

| # | Stage 2 Hypothesis | Verdict criteria |
|---|-------------------|------------------|
| H1 | Profitability — Operating margins recover post-Automotive | **CONFIRMED** if op margin ≥ FY2024 AND > 5.5% AND ROE > 6% |
| H2 | Leverage manageable post-divestiture | **CONFIRMED** if TIE > 4x AND total debt ratio < 55% AND LT debt YoY ↓ |
| H3 | ROCE recovers toward 14% via Automotive exit | **CONFIRMED** only if Du Pont shows **BOTH** margin (EBIT/Sales) AND capital turn (Sales/Capital Employed) improved; **INCONCLUSIVE** if only one improved; **REJECTED** if neither or ROCE < FY2024 |

### 8c. Trend Commentary

Compare FY2025 vs FY2024 for **≥6 ratios**. Identify **2 most significant improvements** + **1 most significant concern**, each with ratio value + 1-sentence business explanation.

---

### 9. Du Pont Decomposition

```
ROE = RATIO_leverage × RATIO_asset_turnover × RATIO_operating_profit_margin × RATIO_debt_burden
    = 1.91x × 0.77x × 5.60% × 0.829 = 6.80%
```

Required: (1) state each driver + interpretation; (2) identify **operating margin (5.60%) as binding constraint** (peer ~10%); (3) **counterfactual** — if margin → 10%: ROE → 12.2% (**+540 bps**); (4) reconcile direct vs Du Pont (6 bps gap) as denominator timing.

---

### 10. Strategic Recommendation Requirements

Must include:

1. **One-sentence thesis** — BUY / HOLD / CAUTIOUS HOLD on SKF fundamentals
2. **Cite ≥3 ratio findings** as evidence (e.g., EVA (1,835); op margin 5.60%; TIE 5.64x)
3. **Identify 1 material risk** — e.g., EVA persistence; inventory 153 days; cyclical concentration
4. **Connect to Stage 2 hypothesis** — Reference H1/H2/H3 verdict from §8b
5. **Forward-looking** — Name 1 KPI to monitor FY2026 (recommend: op margin trajectory toward 10%)

Each rec: **evidence + quantified (bps/MSEK) + actionable lever + time-bound**.

---

### 11. Output Format

**File:** `analysis/2026-06-XX-dang-skf-final-analysis.md` (Markdown)

```
# AB SKF FY2025 Performance Ratio Analysis
## Validation Checklist [V1–V9]
## Ratio Results by Category (5 sub-sections)
## Du Pont Decomposition
## Hypothesis Evaluation (H1 / H2 / H3)
## FY2025 vs FY2024 Trend Analysis
## Sensitivity Analysis (per §12)
## Strategic Recommendation
## Appendix: 30 Ratios + FY2024 benchmarks
```

**Length:** 1,500–2,500 words excluding Appendix. **Tone:** Professional analyst memo, no hedging. All numbers cite MSEK or %.

---

### 12. Sensitivity Specification (post-rubric extension)

Uncertainty-aware analysis on the negative-EVA finding — robustness check on the 9.0% WACC assumption.

| Input | Point | Range | Distribution |
|-------|------:|------:|--------------|
| `cost_capital` | 9.00% | 7.0% – 11.0% | Triangular, mode 9.0% |
| `tax_rate` | 33.86% | 30.0% – 37.0% | Uniform |

**Required outputs:**

1. **Tornado chart** — Which input moves EVA most (expected: `cost_capital` dominant). Tool: Excel native bar chart.
2. **5,000-trial Monte Carlo** of EVA — Report P10 / P50 / P90 (MSEK). Tool: Python (numpy + matplotlib) or Excel @RISK add-in.
3. **Narrative:** At what `cost_capital` does EVA cross zero? *(Answer: 5,128 / 77,368 = **6.63%** = ROC. Below this, SKF creates economic value.)*
4. **Interpretation:** Is negative EVA robust to reasonable WACC variation, or an artifact of the 9.0% assumption?

---

## Revision Log

| Version | Date | Change |
|---------|------|--------|
| 1.0 | 2026-05-24 | Initial 11-section spec |
| 2.0 | 2026-05-24 | Added §6g interpretation guide, §8b hypothesis evaluation (H1/H2/H3 with BOTH-component test for H3), §8c trend commentary, V7-V9 validation rules, §12 sensitivity (portfolio extension on WACC robustness), named-range column in §3, revision log. Trimmed for word band. |

*End of specification. Self-contained for Stage 5 LLM ingestion.*
