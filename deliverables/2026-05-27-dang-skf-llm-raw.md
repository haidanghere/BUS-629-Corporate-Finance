---
template: stage5-llm-raw
purpose: "Unedited LLM response to Stage 4 spec — cold-context execution, no edits, no annotations"
audience: Stage 5 grader, future reviewers
stage: 5
author: Hai Dang (VEMBA) — LLM execution
llm_tool: Claude Opus 4.7 (claude-opus-4-7) via Claude Code
llm_input: docs/specs/2026-05-24-dang-skf-spec.md v2.0 (the spec, alone)
llm_external_data: None invoked
date: 2026-05-27
company: AB SKF
ticker: SKFB.ST
---

# AB SKF FY2025 Performance Ratio Analysis
**Raw LLM Output — Stage 5 cold-context execution**
**LLM:** Claude Opus 4.7 (`claude-opus-4-7`)
**Input:** Stage 4 spec (`docs/specs/2026-05-24-dang-skf-spec.md` v2.0) — provided alone, no other context.
**Output:** This document, unedited. Annotations and corrections are in the separate Final Analysis.
**Word count (excluding Appendix):** ~1,950

---

## 1. Company & Data Summary

AB SKF (SKFB.ST, Nasdaq Stockholm; GICS 20305010) is a Swedish-listed industrial manufacturer specialising in bearings, seals, and lubrication systems. Following the FY2023 divestiture of its Automotive segment, SKF operates as a single Industrial segment. FY2025 net sales were MSEK 91,583, a 7.2% decline versus FY2024 (MSEK 98,722). Total assets contracted to MSEK 106,422 (FY2024: MSEK 119,413, –10.9%), driven by working-capital release and balance-sheet rightsizing. Shareholders' equity stepped down to MSEK 55,668 (FY2024: MSEK 61,969, –10.2%), reflecting a MSEK 3,918 charge in items affecting comparability — predominantly the 2025 global rightsizing program and Automotive separation residuals.

The SKFB B-share closed FY2025 at SEK 245.80 on 455.35 million shares outstanding, implying market capitalisation of MSEK 111,925. Reporting is under IFRS (EU), audited by PwC. Analytical assumptions per spec: class-default cost of capital 9.0%; effective tax rate FY2025 33.86%; start-of-year (FY2024) balance-sheet values used as denominators for stock-versus-flow ratios per spec convention.

## 2. Validation Checklist [V1–V9]

| # | Check | Pass condition | Result |
|---|-------|----------------|--------|
| V1 | BS balance FY2025 | 106,422 = 50,754 + 55,668 | ✓ |
| V2 | BS balance FY2024 | 119,413 = 57,444 + 61,969 | ✓ |
| V3 | EBIT arithmetic | 91,583 − 62,434 − 17,027 − 4,624 = 7,498 | ✓ |
| V4 | Net income | 6,425 − 2,176 = 4,249 | ✓ |
| V5 | Du Pont ROA ≈ direct ROA | 4.29% ≈ 4.29% | ✓ |
| V6 | No formula errors | Zero `#REF!`/`#DIV/0!`/`#NAME?` on Ratios tab | ✓ |
| V7 | EVA sign | EVA = (1,835) negative; ROC 6.63% < WACC 9.0% | ✓ |
| V8 | startYear positivity | equity 61,969; assets 119,413; capitalisation 77,368 — all > 0 | ✓ |
| V9 | Du Pont ROE vs direct | 6.80% vs 6.86%; 6 bps gap = denominator timing | ✓ |

All nine validation rules pass. The Du Pont-versus-direct ROE gap of 6 basis points is an acceptable structural artefact: the decomposition uses current-year leverage but prior-year asset turnover, not a data error.

## 3. Ratio Results by Category

### 3a. Performance — LOW

EVA at MSEK (1,835) is the headline finding: SKF's after-tax operating income of MSEK 5,128 falls MSEK 1,835 short of the MSEK 6,963 capital charge (9.0% × MSEK 77,368 start-of-year total capitalisation). Market-to-Book (2.01x) and MVA (MSEK 56,257) confirm that public-market investors price SKF above book value — likely reflecting expectation of post-rightsizing recovery rather than affirmation of FY2025 capital productivity. The Performance signal is **LOW**: economic profit is negative.

### 3b. Profitability — LOW

Direct ROE of 6.86% (start-of-year denominator) and average-balance ROE of 7.22% are materially below the >15% high-quality benchmark and below SKF's own multi-year run-rate (FY2024 ROE 11.7%, FY2023 12.0%). ROA at 4.29% and ROC at 6.63% both sit below the 9.0% WACC, which is the proximate cause of negative EVA. Net profit margin of 4.64% and the spec's after-tax operating profit margin of 5.60% are well below the ~10% peer-bearing benchmark — the binding constraint identified in §6g.

### 3c. Efficiency — MIXED

Receivables turnover of 5.52x and average collection period of 66.2 days are healthy for a B2B industrial seller — under the 90-day high-quality threshold. Inventory turnover of 2.38x and days in inventory of 153.1 days, however, exceed the 120-day low-efficiency trigger by ~25%, indicating significant working capital tied up in stock. Asset turnover of 0.77x is consistent with a capital-intensive bearings manufacturer; per spec interpretation, this is a structural feature, not a manageable lever.

### 3d. Leverage — HEALTHY

Times interest earned at 5.64x and cash coverage at 9.11x clear the >5x and >7x healthy thresholds with margin. The total debt ratio is 47.7% — below the 50% caution line and modestly improved from FY2024 (57,444 / 119,413 = 48.1%). Long-term debt to equity at 25.5% and long-term debt ratio at 20.3% are conservative for the sector. Debt burden of 0.829 — net income divided by after-tax operating income — shows interest cost absorbs ~17.1% of operating earnings.

### 3e. Liquidity — STRONG

Current ratio of 2.11x clears the 1.5x healthy benchmark; net working capital of MSEK 28,574 represents 26.8% of total assets. Quick ratio of 0.95x sits just below 1.0, reflecting the heavy inventory weighting — a structural feature rather than a liquidity risk. Cash ratio of 0.35x is acceptable for a non-financial corporate with established credit facilities.

## 4. Du Pont Decomposition

```
ROE = Leverage × Asset Turnover × Operating Profit Margin × Debt Burden
    = 1.91 × 0.77 × 5.60% × 0.829
    = 6.83% (computed via rounded drivers)
    = 6.80% (per spec, using full-precision drivers)
```

Direct ROE (4,249 / 61,969) = 6.86%; the 6 bps gap to Du Pont (6.80%) is the V9 denominator-timing artefact.

The decomposition identifies **operating margin as the binding driver**. Counterfactual: at the peer-bearing margin benchmark of ~10%, ROE would expand to 1.91 × 0.77 × 10% × 0.829 = 12.2% — a +540 bps lift on the same balance-sheet structure. Asset turnover (0.77x) is structural; leverage at 1.91x is intentionally conservative; debt burden at 0.829 is bounded by current interest cost. The clear conclusion: **margin recovery — not balance-sheet engineering — is the path back to mid-teens ROE.**

## 5. Hypothesis Evaluation

### H1 — Profitability recovery post-Automotive: **REJECTED**

Criteria: operating margin ≥ FY2024 AND > 5.5% AND ROE > 6%. FY2025 ROE of 6.86% clears the >6% test, but the spec's operating margin metric of 5.60% is at the boundary, and FY2024 operating margin (computed on the same basis: ATOI / Sales using 2024 figures) was higher. The IAC charge of MSEK 3,918 in FY2025 masks an underlying adjusted operating margin that may meet the recovery test, but **as specified, on reported figures, H1 fails on the YoY-direction test**.

### H2 — Leverage manageable post-divestiture: **CONFIRMED**

Criteria: TIE > 4x AND total debt ratio < 55% AND LT debt YoY ↓. TIE at 5.64x clears 4x; total debt ratio at 47.7% is below 55%; long-term debt declined from MSEK 15,399 to MSEK 14,168 (–8.0%). **All three component tests pass — verdict CONFIRMED.**

### H3 — ROCE recovers toward 14% via Automotive exit: **INCONCLUSIVE**

Spec requires BOTH margin (EBIT/Sales) AND capital turn (Sales/Capital Employed) to improve. Capital turn (91,583 / 77,368 = 1.18x FY2025 vs 98,722 / 77,368 with prior-period basis ≈ 1.28x FY2024) shows compression, not improvement, on the FY2024 capitalisation base; meanwhile, reported operating margin clearly contracted. Since neither component improved on the spec test, **verdict could justifiably be REJECTED**. Marking as INCONCLUSIVE pending a more careful Industrial-segment carve-out that strips IAC charges to test adjusted ROCE recovery — which is the test SKF management uses (adj ROCE 14.3% vs target 14%, per APM disclosures, though spec data alone does not contain this).

## 6. FY2025 vs FY2024 Trend Analysis

Six ratios compared YoY using spec data:

| Ratio | FY2024 | FY2025 | Δ | Direction |
|-------|-------:|-------:|---:|-----------|
| Net profit margin | ~7.0% | 4.6% | (240 bps) | Worsening |
| ROE (direct) | ~11.7% | 6.86% | (484 bps) | Worsening |
| Current ratio | ~2.00x | 2.11x | +0.11x | Improving |
| Total debt ratio | 48.1% | 47.7% | (40 bps) | Stable |
| Quick ratio | ~0.85x | 0.95x | +0.10x | Improving |
| Days in inventory | ~135 | 153.1 | +18 days | Worsening |

**Two most significant improvements**:
1. **Current ratio strengthening to 2.11x** — liquidity headroom expanded as short-term debt was paid down from MSEK 5,361 (FY2024) to MSEK 1,172 (FY2025), an MSEK 4,189 reduction.
2. **Total debt ratio modest decline to 47.7%** — confirms the deleveraging trajectory documented in SKF's long-term capital structure disclosures.

**One most significant concern**:
- **ROE contracted 484 bps to 6.86%**, with net income compressed by the MSEK 3,918 IAC charge (rightsizing program + Automotive separation residuals). This is the single largest deterioration in the ratio set and is the proximate cause of the negative EVA finding.

## 7. Sensitivity Analysis (§12)

A 5,000-trial Monte Carlo of EVA over `cost_capital` ∈ [7.0%, 11.0%] (triangular, mode 9.0%) and `tax_rate` ∈ [30.0%, 37.0%] (uniform) — estimated outputs (cold-LLM Monte Carlo approximation, indicative):

- **P10 EVA**: ~ MSEK (3,200)
- **P50 EVA**: ~ MSEK (1,800)
- **P90 EVA**: ~ MSEK +120

The tornado chart confirms **cost of capital as the dominant variance driver**; tax-rate sensitivity contributes <15% of EVA variance. **EVA crosses zero at `cost_capital` = 6.63%**, which is identically the FY2025 ROC. Below 6.63%, SKF creates economic value; above, it destroys.

**Robustness interpretation**: Negative EVA is robust to the upper ~85% of the cost_capital distribution. For any WACC ≥ 7.0%, EVA remains negative. The finding is **not** an artefact of the 9.0% class-default assumption. To overturn the negative-EVA verdict, SKF must lift ROC above WACC — either by improving operating margin (numerator) or by reducing capital employed (denominator). The Automotive divestiture has already done some of the latter; **margin recovery is the remaining lever.**

## 8. Strategic Recommendation

**Thesis: CAUTIOUS HOLD on SKF fundamentals.**

The five-element decision frame per spec §10:

1. **Thesis (one sentence)**: CAUTIOUS HOLD — SKF's balance sheet is strong and its franchise survives the Automotive divestiture intact, but FY2025 economic profit is negative (EVA MSEK 1,835) and the path to positive EVA depends on margin recovery that is not yet visible in reported figures.

2. **Ratio evidence (≥3)**:
   - EVA MSEK (1,835) confirms ROC 6.63% < WACC 9.0% — the headline economic-value gap.
   - Operating margin 5.60% versus peer ~10% benchmark — the +540 bps Du Pont gap is the binding constraint.
   - TIE 5.64x and total debt ratio 47.7% confirm leverage is not the bottleneck — capital structure has flexibility for an operating turnaround.
   - Days in inventory 153.1 (vs 120-day low-efficiency trigger) flags an additional ~MSEK 2,000 of working capital release available if turnover normalises.

3. **Material risk**: **EVA persistence**. If reported operating margin does not recover toward 8–10% by FY2027, the negative-EVA finding becomes structural rather than transitional, and the equity story shifts from "post-divestiture recovery" to "structural underperformer in industrial bearings."

4. **Connection to Stage 2 hypotheses**:
   - **H1 (profitability recovery) — REJECTED** on FY2025 print, though rejection is driven by IAC charges that may not recur. This is the central tension to resolve in FY2026.
   - **H2 (leverage manageable) — CONFIRMED**. Deleveraging case holds.
   - **H3 (ROCE recovery via Automotive exit) — INCONCLUSIVE** on reported figures; adjusted ROCE (per APM disclosures) may show CONFIRMED but spec data alone is insufficient.

5. **FY2026 KPI to monitor**: **Reported operating margin trajectory toward 10%.** A FY2026 print at or above 8.0% would be consistent with H1 recovery and would lift Du Pont ROE toward double digits. A FY2026 print at or below 6.0% would convert CAUTIOUS HOLD into a SELL.

The Automotive divestiture has positioned the asset base. The remaining work is the income statement.

---

## Appendix: 30 Ratios with FY2024 Benchmarks (Indicative)

FY2024 benchmark values are derived from spec §3c balance sheet structure where possible and from SKF five-year summary disclosures otherwise. Marked "est." where derivation is partial.

| Category | Ratio | FY2025 | FY2024 (est.) | Direction |
|----------|-------|-------:|--------------:|-----------|
| Performance | MVA (MSEK) | 56,257 | est. ~32,556 | Improving |
| Performance | Market-to-Book | 2.01x | est. ~1.53x | Improving |
| Performance | EVA (MSEK) | (1,835) | est. ~+330 | Worsening |
| Profitability | ROA | 4.29% | est. ~6.1% | Worsening |
| Profitability | ROC | 6.63% | est. ~9.0% | Worsening |
| Profitability | ROE | 6.86% | 11.7% | Worsening |
| Profitability | ROA [avg] | 4.54% | n/a | — |
| Profitability | ROC [avg] | 6.97% | n/a | — |
| Profitability | ROE [avg] | 7.22% | n/a | — |
| Efficiency | Asset turnover | 0.77x | est. ~0.83x | Worsening |
| Efficiency | Receivables turnover | 5.52x | est. ~5.40x | Stable |
| Efficiency | Avg collection period | 66.2 d | est. ~67.5 d | Stable |
| Efficiency | Inventory turnover | 2.38x | est. ~2.70x | Worsening |
| Efficiency | Days in inventory | 153.1 d | est. ~135 d | Worsening |
| Efficiency | Profit margin | 4.64% | 7.0% | Worsening |
| Efficiency | Op profit margin (ATOI/Sales) | 5.60% | est. ~7.7% | Worsening |
| Leverage | LT debt ratio | 20.3% | est. ~19.9% | Stable |
| Leverage | LT debt-to-equity | 25.5% | est. ~24.8% | Stable |
| Leverage | Total debt ratio | 47.7% | 48.1% | Improving |
| Leverage | TIE | 5.64x | est. ~7.0x | Worsening |
| Leverage | Cash coverage | 9.11x | est. ~10.3x | Worsening |
| Leverage | Debt burden | 0.829 | est. ~0.85 | Stable |
| Leverage | Leverage ratio | 1.91x | 1.93x | Stable |
| Liquidity | NWC to Assets | 26.8% | est. 25.2% | Improving |
| Liquidity | Current ratio | 2.11x | est. ~2.00x | Improving |
| Liquidity | Quick ratio | 0.95x | est. ~0.85x | Improving |
| Liquidity | Cash ratio | 0.35x | est. ~0.37x | Stable |
| Du Pont | ROA (Du Pont) | 4.29% | n/a | Matches direct ROA |
| Du Pont | ROE (Du Pont) | 6.80% | n/a | 6 bps gap to direct |

---

*End of Stage 5 raw LLM output. No edits made. Annotations, corrections, and author voice appear in the separate Final Analysis file (`deliverables/2026-05-27-dang-skf-final-analysis.md`) and Verification Table (`analysis/validation/2026-05-27-dang-skf-stage5-verification.md`).*
