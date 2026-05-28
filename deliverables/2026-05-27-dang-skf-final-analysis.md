---
template: stage5-final-analysis
purpose: "Stage 5 final analysis — edited, annotated, corrected version of LLM raw output, with strategic judgment in author voice and peer-benchmarked recommendations"
audience: AB SKF CFO & executive committee; Professor Adam Stauffer (course grader)
stage: 5
author: Hai Dang (VEMBA) — Head of People Experience, SKF Vietnam
company: AB SKF (publ.)
ticker: SKFB.ST · Nasdaq Stockholm · GICS 20305010
reporting_standard: IFRS (as adopted by the EU); audited by PwC
currency: MSEK unless noted
fiscal_year_current: FY2025 (Jan 1 – Dec 31, 2025)
fiscal_year_prior: FY2024
date: 2026-05-27
spec_basis: docs/specs/2026-05-24-dang-skf-spec.md v2.0
raw_llm_basis: deliverables/2026-05-27-dang-skf-llm-raw.md
verification_basis: analysis/validation/2026-05-27-dang-skf-stage5-verification.md
peer_benchmark_basis: deliverables/2026-05-27-dang-skf-peer-benchmark.md
word_count_target: ~4,000–4,400 excluding Appendix
---

# AB SKF FY2025 Performance Ratio Analysis — Final
**Stage 5 deliverable · BUS-629 VEMBA · Hai Dang**

---

## 0. Executive Summary

AB SKF's FY2025 ratio analysis prints a uniformly negative reported headline — **EVA of MSEK (1,835), ROE compression to 6.86%, net profit margin of 4.64%, and Du Pont ROE held back by an operating-margin driver of 5.60% (after-tax) against a peer median near 10%**. Taken at face value, the year reads as a structural step-down in capital productivity. The underlying business, on the *adjusted operating margin* basis SKF management publishes (12.7% FY2025 versus 12.3% FY2024 and a 14% long-term target), tells a different story: a year of disciplined cost-base restructuring inside an otherwise rising profitability trajectory. The single most important judgment in this report is which of those two readings the board, the investor base, and the analyst community should anchor on for FY2026.

The peer benchmarking work in [the companion deliverable](2026-05-27-dang-skf-peer-benchmark.md) confirms that the reported-basis underperformance is largely a *European/Japanese bearings cohort condition* — Schaeffler, NSK, NTN and JTEKT all print FY2024 reported operating margins in the 3.4–4.7% range, materially worse than SKF on either reported or adjusted basis. The peer set is the exact competitor universe SKF itself identifies in the Annual Report 2025 (page 5: "Schaeffler, Timken, NSK, NTN and JTEKT"). On the *adjusted* basis SKF moves from 4th of 6 to 2nd of 6 in the peer set, behind only Timken (15.9% structurally premium-mix US bearings+power-transmission).

This analysis lands on **five strategic recommendations**, anchored in the Stage 4 spec output and peer-relative evidence. The primary recommendation is to **commit publicly to FY2026 reported operating margin ≥8.5%** (interim) and 10% (FY2027 exit) as the KPI that bridges reported and adjusted figures and would place SKF above the entire European/Japanese bearings peer cohort on reported numbers alone. *Important distinction*: 8.5% and 10% are **peer-relative outperformance targets**, not EVA-neutrality targets — EVA breakeven requires a higher reported EBIT margin of ~11.5% (equivalent to ROC = 9.0%), achievable as IAC charges fully normalise beyond the FY2027 exit. Capital structure is *not* a constraint — SKF carries the least leverage in the European bearings peer set. The binding lever is operating margin, and the peer evidence supports the rightsizing thesis. *The work in front of SKF is delivery on a margin commitment already made internally; the ratio analysis confirms it.*

---

## 1. Company & Data Summary with Verified Assumptions

AB SKF is the world's largest bearing manufacturer, listed on Nasdaq Stockholm under SKFB and reporting under IFRS (audited by PwC). I work at SKF Vietnam as Head of People Experience — operational context that sharpens my reading of this year's numbers but does not substitute for the analytical discipline of the ratio framework. The FY2025 analysis below treats the spec-defined model as the data spine; my judgment enters where the numbers need translation into business action, and the peer-benchmark companion provides industry-relative anchoring.

**Headline FY2025 figures** (MSEK, IFRS reported):

| Item | FY2025 | FY2024 | Δ% |
|------|-------:|-------:|---:|
| Net sales | 91,583 | 98,722 | (7.2%) |
| EBIT (derived) | 7,498 | ~10,339 | (27.5%) |
| Net income | 4,249 | 6,887 | (38.3%) |
| Total assets | 106,422 | 119,413 | (10.9%) |
| Shareholders' equity | 55,668 | 61,969 | (10.2%) |
| Items affecting comparability (IAC) | (3,918) | (1,844) | — |

**Verified assumptions**:

- Class-default cost of capital `cost_capital` = 9.00% (not SKF's actual WACC — uncertainty-tested in §6 below; SKF's actual WACC sits in the 7.5–8.5% range based on analyst consensus, which does *not* change the EVA sign).
- Effective tax rate FY2025 = 33.86% (elevated vs. FY2024 24.2% due to non-deductible IAC items).
- B-share close SEK 245.80; shares outstanding 455.35M → market cap **MSEK 111,925**. (Spec formula §5 carries a notation defect — `× 1000` is inconsistent with shares-in-millions input — but the output value reconciles. Flagged in retrospective.)
- Start-of-year denominator convention for stock/flow ratios is pinned via `startYear_*` named ranges. This is the most consequential analytical choice — see verification R2, R3 (denominator tests passed).

**Validation V1–V9 all pass** per spec §7. Most consequential: V9 reconciles Du Pont ROE (6.80%) to direct ROE (6.86%) with a 6 bps gap acknowledged as denominator timing, not a data error. Manual verification (verification R8) confirms the precise Du Pont chain at 6.80%; the LLM's secondary "6.83%" figure (rounded-chain artefact) is suppressed in this final analysis.

The FY2025 reading sits inside a *five-year context* that the analytical framework should not lose sight of. Net sales declined 7.2% YoY, but the AR APM disclosures decompose this into **−0.4% organic, −6.6% currency, and −0.2% structure** — currency, not volume, drove the reported decline. The IAC charge of MSEK 3,918 is predominantly the rightsizing program (MSEK 2,946 — verified against AR 2025 page 100 commentary: "MSEK −2,946 (−1,364) related to ongoing restructuring and cost reduction activities, including the full cost of the rightsizing activity in the Industrial business") with the remaining MSEK 1,356 (1,844 vs 1,364 prior year = +480) attributed to the Automotive separation programme costs. **The single largest analytical risk in this report is treating FY2025 as steady-state when management has guided it as a transition year ahead of the planned 2026 Automotive separation.**

**Reconciliation to AR figures** (added post-AR-verification audit): The Stage 3 Excel model uses **EBIT = MSEK 7,498** (= Net sales − COGS − R&D − Selling − Administrative), a "core operating profit" definition that excludes "Other operating income/expenses" (net +196) and "Income from associated companies" (+61). The AR's headline **Operating profit of MSEK 7,755** includes these items. The two definitions differ by MSEK 257 (3.4% of EBIT); all spec-driven ratios (Du Pont, EVA, EBIT margin 8.19%) use the 7,498 base for internal consistency. AR-reported EBIT margin would read 8.5% (7,755 / 91,583). Similarly, the spec's **ROC = 6.63%** is post-tax (ATOI / start-of-year capitalisation); the AR's published **ROCE = 9.6%** is pre-tax (Op Profit + Interest Income / 12-month rolling avg capital employed) — these are different concepts, not different values of the same concept. The spec's EVA framework (ROC ≥ WACC = 9.0% for breakeven) operates entirely on the post-tax basis and is internally consistent; the AR's pre-tax ROCE of 9.6% would translate to ~6.35% post-tax (× 0.6614) at SKF's effective tax rate, close to but not identical to the spec's 6.63% due to denominator-base differences.

---

## 2. Ratio Results & Interpretation

### 2a. Performance — LOW signal

**EVA = MSEK (1,835).** SKF's after-tax operating income of MSEK 5,128.66 falls MSEK 1,834.46 short of the MSEK 6,963.12 capital charge (9.0% × MSEK 77,368 start-of-year capitalisation). Rounded to integer MSEK, EVA is **(1,835)**, matching spec and LLM. **Market-to-Book 2.01x and MVA MSEK 56,257** confirm that investors price SKF above book — this is **forward-looking expectation, not affirmation** of FY2025 capital productivity. The gap between negative economic profit and positive market premium is the analytical centre of this report.

**Peer context**: Inside the bearings peer set (Schaeffler, NSK, NTN, JTEKT, Timken — per SKF's own AR 2025 competitor list), only Timken generates consistently positive EVA across the cycle (Timken ROC of ~13% post-tax against rough WACC equivalents). Schaeffler, NSK, NTN, and JTEKT are all *materially more negative* than SKF on an EVA basis after FY2024 cyclical compression. **SKF's EVA gap is real but is one of the smaller gaps in the European/Japanese cohort** — and is plausibly bridgeable by the FY2025 rightsizing program as IAC charges normalise plus the FY2027+ post-Automotive-separation Industrial-only run-rate uplift.

### 2b. Profitability — LOW (reported); MIDDLE QUARTILE (adjusted, peer-relative)

Direct **ROE 6.86%** (start-of-year denominator) sits well below the >15% high-quality threshold and below SKF's three-year average (FY2023–24: ~11.9%). Average-balance **ROE 7.22%** is the more conservative read. **ROA 4.29%** and **ROC 6.63%** both fall below the 9.0% WACC — the proximate cause of negative EVA. **Net profit margin 4.64%** is the lowest of the five-year window. The **spec's after-tax operating margin (ATOI/Sales) of 5.60%** is the figure used in Du Pont; the more conventional EBIT/Sales reads 8.19% (7,498/91,583). I will reference both with the spec definition for Du Pont consistency, but I want to be explicit that **5.60% is not "operating margin" in the standard CFA sense** — it is an after-tax measure designed for ROC continuity.

**Peer context**: SKF's reported FY2024 ROE of 11.7% placed it second only to Timken (14.1%) and well ahead of Schaeffler (3.2%), NSK (3.7%), and JTEKT (3.1%). FY2025 compression to 6.86% drops SKF to third, still *materially above* the European/Japanese cohort. On the adjusted operating margin basis (12.7%), SKF's profitability ranking *strengthens* — second only to the structurally premium American pair. **The reported-basis story understates SKF's peer-relative profitability; the adjusted-basis story does not.**

### 2c. Efficiency — MIXED

**Receivables turnover 5.52x / collection 66.2 days** are healthy for a B2B industrial seller — below the 90-day quality line and roughly in line with peer median (Timken 58 days, JTEKT 71 days). **Inventory turnover 2.38x / days 153.1** breach the 120-day low-efficiency trigger by ~28%. **Asset turnover 0.77x** is consistent with capital-intensive manufacturing and sits at the bearings-peer median. The inventory bloat is the actionable efficiency lever — see R2 below. **Note**: the 153-day calc uses start-of-year inventory (26,182); the current-year inventory of 23,677 already implies a forward run-rate closer to **138 days** (23,677 / 171.05), so SKF's working capital trajectory is improving — the lagged ratio understates this.

**Peer context**: Inventory days at 153 (lagged) compares unfavourably to Timken (95 days) — a *58-day gap* equating to MSEK 7,427 of excess inventory at year-end FY2025 versus the Timken-parity target (the working capital release potential quantified in R2 below). Even on the forward run-rate, SKF's 138 days is 43 days slower than Timken, 20 days slower than JTEKT (118), and 10 days slower than Schaeffler (128). **Inventory efficiency is SKF's one structural peer-relative gap inside the ratio set.**

### 2d. Leverage — HEALTHY

**TIE 5.64x** clears the >5x high-quality threshold; **cash coverage 9.11x** is comfortable. **Total debt ratio 47.7%** is below the 50% caution line. Long-term debt declined from MSEK 15,399 to MSEK 14,168 (–8.0% YoY) and short-term debt from MSEK 5,361 to MSEK 1,172 (–78.1%). **Debt burden 0.829** says interest absorbs ~17% of operating earnings. Leverage is **not the problem** — it is the only category where SKF reads HEALTHY on every component.

**Peer context**: SKF carries the **least leverage in the European bearings peer set**. Schaeffler's combined-entity FY2024 reading of 67% total debt ratio and 2.9x TIE is materially weaker; Timken (52%) operates at higher leverage by choice and US-market norm; the Japanese cohort (NSK 50%, JTEKT 56%, NTN 59%) sits in the 50–60% band. SKF's capital structure offers **optionality** — for accretive M&A, buybacks, or dividend resilience through the planned 2026 Automotive separation — without leverage-driven distress risk. The peer evidence confirms that capital structure is not the bottleneck on FY2025 returns; reducing leverage further would *destroy* optionality without lifting ROE.

### 2e. Liquidity — STRONG

**Current ratio 2.11x** and net working capital MSEK 28,574 (26.8% of assets) clear all thresholds. **Quick ratio 0.95x** sits just below 1.0 — reflecting heavy inventory, not stress. **Cash ratio 0.35x** is normal for an industrial corporate with established facilities. SKF can absorb a multi-quarter demand shock without a liquidity event. The peer set confirms SKF is at the upper end of the current-ratio range (NSK 1.95x, JTEKT 1.62x, NTN 1.55x, Schaeffler 1.34x, Timken 2.46x); SKF would be a stronger liquidity name only by carrying more cash, which is not value-creating.

### 2f. Du Pont System — MARGIN-LIMITED

See §3 below. ROE (6.80%) is held down by the operating-margin driver (5.60%) and is **not** a leverage, turnover, or debt-burden problem.

---

## 3. Du Pont Decomposition and Soundness

```
ROE = Leverage × Asset Turnover × Operating Profit Margin × Debt Burden
    = 1.91136 × 0.76695 × 5.601% × 0.82850
    = 6.80%
```

Manual verification (R8) confirms 6.80% at full precision. The 6 bps gap to direct ROE 6.86% is the V9 denominator-timing artefact — Du Pont uses **current-year** leverage with **prior-year** asset turnover. The asymmetry is documented in the spec (Notes tab, V9 pass condition). The LLM raw output transparently surfaced both the precise (6.80%) and rounded-chain (6.83%) figures; in this final analysis the precise figure is retained and the rounded artefact is suppressed.

**Driver assessment**:

- **Leverage 1.91x**: intentionally conservative. SKF's industrial peers (Schaeffler ~2.4x, NSK 2.1x, NTN 2.4x, JTEKT 2.3x, Timken 2.3x) operate broadly in the 2.0–2.5x range. SKF is under-levered against the peer median if anything — there is room to increase capital efficiency through buybacks or higher debt, but not at the cost of the single-A credit rating.
- **Asset turnover 0.77x**: structural. Capital-intensive bearings manufacturing does not turn 1.0x+. Peer median 0.74x (Timken 0.88x highest, NTN 0.65x lowest). Move on.
- **Debt burden 0.829**: stable; bounded by current interest cost. With LT debt falling 8% YoY, this will tick toward 0.85+ in FY2026 absent rate moves.
- **Operating margin (ATOI/Sales) 5.60%**: **binding constraint**. Peer median is ~10%; American pair ~13–16%; European/Japanese cohort ~3–5%. This is the only Du Pont driver that meaningfully moves ROE.

**Counterfactual**: if the spec's ATOI/Sales driver recovers to a peer-benchmark 10% (a post-tax operating margin threshold, equivalent to a pre-tax operating margin of ~15.1% at SKF's 33.86% effective tax rate), Du Pont ROE becomes:

```
1.911 × 0.767 × 10% × 0.829 = 12.19% → +539 bps
```

This is the **single most important number in the analysis**. Tax-basis note: the spec defines its "operating margin" driver on a **post-tax ATOI/Sales basis** (5.60% FY2025), so the 10% counterfactual is also post-tax; SKF's published adjusted operating margin of 12.7% is *pre-tax*, equivalent to ~8.4% post-tax at the current effective tax rate. To hit the 10% post-tax counterfactual on a like-for-like basis, SKF would need a **pre-tax reported EBIT margin of ~15.1%** (= 10% / 0.6614) against the FY2025 reported EBIT margin of 8.2% — a **~7 pp lift**. This is more ambitious than the EVA breakeven case in §6 (which requires only ~3 pp of EBIT margin lift to ROC = 9.0% and ROE ~9.2%); the 12.2% Du Pont counterfactual is a genuine mid-teens ROE target, not the breakeven case. The 10% post-tax counterfactual is therefore a *stretch* against SKF's adjusted pre-tax run-rate — not "already there" on a like-for-like basis, but inside the achievable range as the rightsizing savings flow through and the IAC charges normalise. The peer benchmark shows European/Japanese peers in the 3–6% pre-tax operating-margin band and American peers in the 16–20% band, with SKF's adjusted pre-tax 12.7% sitting between the two — SKF's transition target should bridge to the upper end of the European/Japanese band in FY2026–27 and approach the American band as a multi-cycle aspirational frame.

**Soundness check**: Du Pont reads MARGIN-LIMITED, not LEVERAGE-LIMITED or TURNOVER-LIMITED. The *directional* conclusion (margin is the binding constraint) is robust to the choice of operating-margin definition; the *specific ROE number* of 6.80% requires the spec's ATOI/Sales 5.60% convention to reconcile with direct ROE under the V9 check (using EBIT/Sales 8.19% would produce a pre-tax decomposition that does not tie to the after-tax ROE 6.86% the analysis is built on). The conclusion is also independent of the denominator-timing artefact. The peer benchmark supports the same directional conclusion at a higher level: every peer with high ROE generates it through margin, not through outsized leverage or turnover.

---

## 4. Hypothesis Evaluation (Stage 2 H1 / H2 / H3)

**H1 — Profitability recovery post-Automotive: REJECTED (on reported figures, with caveat).**
Test: operating margin ≥ FY2024 AND > 5.5% AND ROE > 6%. FY2025 ATOI margin 5.60% is at the threshold; ROE 6.86% clears the >6% test; but YoY direction is **down**, not recovery. **However**: the FY2025 IAC charge of MSEK 3,918 — predominantly the rightsizing program (MSEK 2,946) — is a discrete, disclosed one-off. On the adjusted-operating-margin basis SKF management publishes (APM disclosures), FY2025 reads 12.7% vs. FY2024 12.3% — H1 would CONFIRM. **The spec test failed because it ran on reported figures only**; I note this honestly as a spec limitation, not a hypothesis failure. The economic reality is closer to "confirmation pending one-off normalisation."

The *peer overlay* changes the interpretation further. Against the European/Japanese cohort (Schaeffler 4.7%, NSK 4.5%, JTEKT 3.6% — all reported figures FY2024), SKF's reported operating margin of 5.60% (FY2025 ATOI basis) or 8.2% (FY2025 EBIT basis) already *outperforms* the cohort. The H1 hypothesis was framed against a structural-recovery test that did not encode a peer-relative target. Reframed as "is SKF's profitability competitive against the European/Japanese cohort," the answer is *yes on both bases*.

**H2 — Leverage manageable through Automotive separation: CONFIRMED.**
TIE 5.64x > 4x; total debt ratio 47.7% < 55%; LT debt declined 8.0% YoY. All three component tests pass. The LLM verdict (CONFIRMED) is correct. The peer benchmark adds context: SKF holds the least leverage in the European cohort and one of the most conservative profiles in the global bearings peer set, providing balance-sheet headroom heading into the planned 2026 Automotive separation. H2 confirmation is *unambiguous* and the peer evidence sharpens it. (Note: the original Stage 2 hypothesis was framed around a "post-divestiture" Automotive status; the AR 2025 confirms the separation is *planned for 2026*, not yet executed — the leverage-resilience question therefore remains relevant rather than retrospective.)

**H3 — ROCE recovers toward 14% via planned Automotive separation: INCONCLUSIVE on reported, PARTIAL CONFIRMATION on adjusted.**
The strict BOTH-component test (margin AND capital turn improvement) fails on reported figures — margin contracted, capital turn shows compression on the prior-period capitalisation base. The LLM correctly issued INCONCLUSIVE and flagged the adjusted-figure pathway. **My addition** (post-AR verification): SKF's published adjusted ROCE FY2025 is 14.3% (vs FY2024 14.2%) per AR 2025 page 153 — already at the 14% level. *Important correction from the original Stage 5 framing*: per AR 2025 page 5, SKF's published 14% long-term target is for **adjusted operating margin** (currently 12.7%, **below** target), not for ROCE. The adjusted ROCE happens to print at ~14% but is not the metric anchored to the published 14% target. So H3 reframed honestly: adjusted ROCE has been at the 14% level for two consecutive years (a positive signal), but the published management target of 14% adjusted operating margin remains unmet — H3 reads as **PARTIAL CONFIRMATION on the adjusted ROCE measure, with the explicit adjusted-operating-margin 14% target still pending delivery via the FY2026–27 trajectory toward post-separation Industrial-only profitability.**

**Aggregate hypothesis read**: One of three confirmed on reported figures (H2); two of three confirmed on adjusted figures (H1 + H3 + H2). The reported/adjusted divergence is the analytical centrepiece of FY2025 — not because adjusted figures hide reality, but because the rightsizing program is a *disclosed, bracketed, one-off* and the adjusted basis tests the underlying business question more directly than the reported basis does.

---

## 5. FY2025 vs. FY2024 Trend Analysis

Six ratios YoY:

| Ratio | FY2024 | FY2025 | Δ | Read |
|-------|-------:|-------:|---:|------|
| Net profit margin | 7.0% | 4.6% | (240 bps) | Worsening |
| ROE (direct) | 11.7% | 6.86% | (484 bps) | Worsening |
| Current ratio | ~2.00x | 2.11x | +0.11x | Improving |
| Total debt ratio | 48.1% | 47.7% | (40 bps) | Stable→Improving |
| Days in inventory | ~135 | 153.1 | +18 days | Worsening (lagged) |
| Net debt/EBITDA | 1.1x | 1.0x | (0.1x) | Improving |

**Two most significant improvements** (per spec §8c):

1. **Net debt/EBITDA 1.0x** — fifth consecutive year of deleveraging (1.5x → 1.0x since FY2022 per AR 2025 Seven-Year Review). Capital structure is at its strongest point in the analytical window. Peer-relative context: this places SKF at the *bottom* of the peer set on leverage (lowest debt = best on this metric) — better than Timken (1.9x), NTN (2.0x), JTEKT (1.6x), NSK (1.1x), and dramatically better than Schaeffler (3.4x post-Vitesco).

2. **Short-term debt reduction from MSEK 5,361 to MSEK 1,172** (–78.1%) — the proximate cause of the current-ratio improvement to 2.11x. This is disciplined capital allocation, not accident. The reduction reflects the AR-disclosed repayment of bonds (MSEK −3,483 per AR page 102) and active debt management; it is not driven by a specific divestiture proceed since the larger Automotive separation is planned for 2026, not yet executed.

**One most significant concern**:

- **ROE compression of 484 bps to 6.86%.** Net income fell MSEK 2,638 YoY; the FY2025 IAC charge of MSEK 3,918 explains the entire decline (with operating income partly absorbing it). The diagnostic question is whether FY2026 reverses this — see R1 below. The peer-relative pattern is *informative*: Schaeffler, NSK, and JTEKT also saw ROE compression in FY2024 (all to single digits), but SKF's compression *path* (one large bracketed IAC year versus multi-year secular pressure) is materially more reversible than the European/Japanese peer pattern.

**Trend reads not flagged in the top three but worth noting**:

- **Asset turnover compression from ~0.83x to 0.77x** — primarily a revenue-decline artefact (numerator), since total assets fell only 10.9% versus the 7.2% sales decline. This will reverse if FY2026 revenue stabilises.
- **Days-in-inventory worsening from ~135 to 153** — *but on a forward run-rate basis using current-period inventory, the figure already reads 138 days*, suggesting the YoY deterioration is partly a denominator-timing effect rather than operational drift. Worth flagging for FY2026 trend reads.
- **Adjusted operating margin trajectory** (not in the reported-basis trend table but central to the FY2025 narrative): 12.3% → 12.7% YoY — an improvement when the reported margin deteriorated. This is the bridge that the FY2026 investor communication has to make.

---

## 6. Sensitivity Analysis (Spec §12)

A 5,000-trial Monte Carlo on EVA over `cost_capital` ∈ [7.0%, 11.0%] (triangular, mode 9.0%) and `tax_rate` ∈ [30.0%, 37.0%] (uniform), per spec §12 design. **The LLM raw output presented illustrative P10/P50/P90 figures without running the simulation** — I flag this and use the algebraic breakeven instead, which is the more diagnostic result and reproducible without simulation tooling.

**Algebraic breakeven**: EVA = 0 when `cost_capital = ROC = 6.63%`. This is the diagnostic insight. The class-default 9.0% places SKF MSEK ~1,835 below breakeven; the implied SKF actual WACC (analyst consensus ~7.5–8.5% for industrial European caps) places SKF still negative by MSEK 700–1,400. **Negative EVA is not an artefact of the 9.0% assumption** — it holds across the realistic WACC range.

**The lever is not WACC. The lever is ROC.** To clear the 9.0% WACC, SKF needs ROC ≥ 9.0% — which from `ATOI / startYear_capitalization` requires ATOI ≥ 9.0% × 77,368 = **MSEK 6,963** vs current 5,128. That is a MSEK 1,835 improvement in after-tax operating income, equivalent to an EBIT increase of ~MSEK 2,777 (at a 33.86% tax assumption) or ~3 percentage points of EBIT margin on FY2025 sales (8.2% → 11.5% pre-tax). **At SKF's published adjusted FY2025 operating margin of 12.7% pre-tax, the adjusted-basis pro forma sits just above EVA breakeven** — but the reported-basis EVA we're optimising for is still MSEK 1,835 below breakeven. The gap is reported-vs-adjusted, i.e. the IAC charges normalising out over multiple periods.

**Single-variable sensitivity (ROC, holding WACC at base 9.0%)**: EVA = (ROC − WACC) × startYear_capitalisation = (ROC − 9.0%) × MSEK 77,368. Each 1 pp of ROC improvement = **MSEK 774 of EVA improvement**. EVA crosses zero at ROC = 9.0% (= WACC); at ROC = 10% EVA = +MSEK 774; at ROC = 12% EVA = +MSEK 2,321. Moving from current ROC 6.63% to ROC = 10% requires MSEK 2,608 of EVA improvement — material but inside the achievable range as the rightsizing-program savings normalise into ATOI. *Tax-basis note*: ROC here is the spec's post-tax measure (ATOI / Capital); SKF's published adjusted ROCE of 14.3% is pre-tax, equivalent to ~9.5% post-tax at SKF's 33.86% effective tax rate. The adjusted run-rate would therefore place SKF just above EVA breakeven on a like-for-like basis, not at ROC = 12% territory. **The path to positive EVA runs through ROC, not WACC or tax** — exactly the Du Pont conclusion of §3. A two-factor WACC × tax sweep adds little above this single-variable read because both alternative inputs are bounded inside narrow realistic ranges (WACC 7.5–10.5%, tax 30–37%) that all leave EVA negative at the current ROC of 6.63%.

---

## 7. LLM Evaluation & Annotations

The LLM's cold-context execution of the spec was **broadly faithful and analytically competent**. Verification confirmed 7 of 9 sampled ratios at exact precision and 1 within rounding. Specific calls:

**What the LLM did well**:
- Correctly applied start-of-year denominators across ROE, ROA, ROC, asset turnover, inventory turnover — the spec's `startYear_*` discipline held.
- Correctly executed the daily-COGS unit conversion in days-in-inventory (153.1) — avoided the common error of using sales-daily.
- Cleanly assigned interpretation labels per §6g (LOW/MIXED/HEALTHY/STRONG/MARGIN-LIMITED).
- Faithfully ran the H1/H2/H3 verdict framework — including the appropriate INCONCLUSIVE on H3 when the BOTH-component test failed.
- Correctly identified margin as the binding Du Pont driver and computed the +540 bps counterfactual at 10% peer-margin parity.

**Where the LLM deviated or showed weakness**:
- **R8 chained-rounding Du Pont ROE 6.83% vs. precise 6.80%** — the LLM transparently reported both figures, but presenting both is not the right answer; one should be picked. I retain 6.80% per spec.
- **§7 Sensitivity P10/P50/P90 were illustrative, not simulated** — the LLM did not run an actual 5,000-trial Monte Carlo and used estimates labelled "indicative." I replaced this with the algebraic breakeven (EVA = 0 at ROC = 6.63%) and a single-variable ROC sensitivity (each 1 pp of ROC = MSEK 774 of EVA improvement), both of which are diagnostic and reproducible without a simulation tool.
- **FY2024 appendix benchmarks marked "est."** — the LLM hedged where it lacked precise comparable values; this is honest but means the YoY directional reads in the trend analysis (§5) need source-document confirmation. I cross-checked against `data/skf-financial-summary-2021-2025.md` and confirm.
- **Hypothesis evaluations did not differentiate reported vs. adjusted figures** — the LLM ran the spec test mechanically (correctly), but did not note that SKF management publishes adjusted figures that would change the verdict on H1 and H3. This is the single biggest gap between LLM execution and CFO-grade analysis — and the place where author judgment most clearly added value.
- **No peer-relative framing** — the LLM operated entirely on absolute thresholds (>15% ROE = high quality, >120 days inventory = low efficiency) without anchoring to bearings-industry comparables. The peer-benchmark companion deliverable was authored separately and *not* requested by the spec, but it materially changes the strategic conclusions — see R1, R2, R5 below.

**Spec defects surfaced** (independent of LLM accuracy):
- §5 market-cap formula uses `× 1000` inconsistent with shares-in-millions input — flagged in retrospective.
- The 5.60% "operating profit margin" naming is non-standard (this is ATOI/Sales, not EBIT/Sales) — risk of misinterpretation by a reader unfamiliar with the spec's after-tax convention.

---

## 8. Strategic Recommendations

Each recommendation cites ratio evidence under `[Data]` and the LLM-versus-author attribution under `[LLM]`. Recommendations are ordered by ratio-driven priority, not strategic horizon — R1 is the highest-leverage action; R5 is the longest-horizon mix-shift play.

### R1 — Operating Margin Recovery Plan (primary lever)

**Action**: Disclose to investors a FY2026 reported operating margin trajectory toward 8.5% (interim) and 10% (FY2027 exit), driven by rightsizing-program savings landing in COGS/SG&A run-rate. Anchor the external KPI on reported figures to bridge the IAC normalisation pathway publicly. *Frame these as peer-relative outperformance targets, not as EVA-neutrality targets* — see [Data] for the distinction.

**[Data]**: Operating margin (ATOI/Sales) 5.60% — binding Du Pont driver. Counterfactual at 10% post-tax margin: ROE expands +539 bps to 12.2%. **EVA breakeven** requires ROC ≥ 9.0%, which equates to ATOI MSEK 6,963 vs. current MSEK 5,128 — a MSEK 1,835 ATOI gap, equivalent to a **reported EBIT margin of ~11.5%** (= 9.0% × 77,368 / 91,583 / 0.6614). The FY2026 8.5% reported KPI and the FY2027 10% exit target do **not** reach EVA breakeven on a like-for-like basis (10% reported → ROC ~7.8%, still below 9.0% WACC); they reach **peer-relative outperformance** — both targets place SKF above the entire European/Japanese cohort (Schaeffler 4.7%, NSK 4.5%, JTEKT 3.6% reported FY2024) on reported figures. EVA neutrality requires further margin expansion beyond the 10% reported target, achievable as IAC charges normalise and rightsizing savings flow through to run-rate.

**[LLM]**: The LLM identified margin as the binding constraint and produced the +540 bps counterfactual correctly. It **did not** quantify the EVA-breakeven margin (~6.8% post-tax ATOI lift; equivalently ROC = 9.0%; ~11.5% reported EBIT margin), which is the more diagnostic number for executive communication. It **did not** anchor the FY2026 target against peer benchmarks, and it **did not** distinguish peer-relative outperformance targets from EVA-neutrality targets. **Author adds**: the EVA-breakeven calculation, the peer-relative reported-margin ladder (8.5% FY2026 → 10% FY2027 → 11.5% EVA-breakeven → 16–20% American-peer pre-tax band as multi-cycle frame), and the explicit distinction between peer-relative and EVA-neutrality targets.

### R2 — Inventory Working Capital Release

**Action**: Drive inventory days from 153 (lagged) / 138 (forward run-rate) toward bearing-peer-benchmark of 120 days within FY2026, with a longer-horizon stretch target of 95 days (Timken parity) by FY2028.

**[Data]**: Days in inventory 153.1 vs. 120-day low-efficiency trigger. At 120 days × daily COGS 171.05 = MSEK 20,526 target inventory; current MSEK 23,677 → **MSEK 3,151 of working capital release potential at 120-day parity**. At full Timken-parity 95 days × 171.05 = MSEK 16,250 target → **MSEK 7,427 of release potential at 95-day parity** (of which MSEK 4,276 is the incremental release from 120-day to 95-day over the longer horizon). At a 7% WACC, the 120-day release is MSEK 220 of recurring capital-charge reduction; the 95-day stretch release is MSEK 520. Peer benchmark confirms inventory days as SKF's one structural efficiency gap — the 58-day delta to Timken is the single most quantifiable peer-parity opportunity in the analysis.

**[LLM]**: The LLM cited the inventory-days issue and estimated MSEK 2,000 of release potential — directionally right but undersized. **Author adds**: peer-anchored sizing (MSEK 3,151 at 120-day European parity, MSEK 7,427 at Timken parity) using forward-run-rate inventory rather than lagged, plus the two-step horizon framing.

### R3 — Dividend Policy Review Conditional on FY2026 EVA

**Action**: If FY2026 EVA remains negative, communicate a temporary dividend hold or reduction from the current ~83% payout ratio (MSEK 3,529 / MSEK 4,249 = 83% on FY2025 reported income) to a 50–60% range until ROC clears 9.0%. Frame the policy review as *capital discipline*, not distress signalling.

**[Data]**: Negative EVA MSEK (1,835); 83% payout on reported net income; the dividend distributes more than economic profit by design. Sustainable only if FY2026+ income recovers; not sustainable if H1 rejection holds on reported basis. Peer benchmark places SKF's dividend yield at ~3.5% (FY2025 SEK 7.75 proposed) — *normal* for the bearings peer set (Schaeffler 4.8% stressed, NSK 3.2%, JTEKT 3.6%, NTN 2.8%, Timken 1.7%) and modestly above the median. Dividend optionality exists; the question is whether to *use* the optionality conditionally.

**[LLM]**: **The LLM did not address dividend policy at all**. This is the most significant author addition — a recommendation that arises directly from connecting EVA to capital-allocation choice, which the spec did not pre-specify. The dividend question matters most to the audience the spec named (CFO + executive committee). **Author originates** the recommendation in full.

### R4 — Investor Communication: Adjusted vs. Reported Bridge

**Action**: In FY2025 results communication, lead with adjusted operating margin 12.7% (against SKF's published 14% long-term adjusted-operating-margin target — currently below target, recovery trajectory disclosed) and adjusted ROCE 14.3% (above the FY2024 reading of 14.2% and consistent with the AR's published ROCE trend); use reported figures only with explicit IAC bridge. Provide a quarterly tracking table that ties reported to adjusted across operating margin, ROE, ROCE, and EVA-equivalent measures.

**[Data]**: Reported operating margin 5.60% (ATOI basis) or 8.2% (EBIT basis) vs. adjusted 12.7% — 710 bps gap explained by MSEK 3,918 IAC charges. Reported ROCE ~9.6% vs. adjusted 14.3%. The reported-vs-adjusted gap is the single biggest source of investor confusion in this print, and the peer benchmark *amplifies* its importance — SKF's peer-relative position shifts from 4th of 6 to 2nd of 6 between the two bases.

**[LLM]**: The LLM ran the spec test on reported figures only and flagged that the spec data did not contain adjusted figures. This is correct on the spec's terms but a gap in the analysis the recipient needs. **Author adds** the adjusted-figure overlay from APM disclosures, the peer-relative-position-shift framing, and the quarterly bridge-tracker recommendation.

### R5 — Aftermarket and Services Mix Shift to Close Structural Peer Margin Gap

**Action**: Accelerate the Connected Technologies / aftermarket services growth program (condition monitoring, digital services, lifecycle contracts) to close the structural margin gap to Timken-style integrated-bearings-plus-PT peers over the FY2027–FY2030 horizon. Disclose Connected Technologies revenue and margin contribution separately in segment reporting starting FY2026.

**[Data]**: Peer benchmark identifies the structural margin gap to Timken (15.9% reported, vs. SKF reported 8.5% / adjusted 12.7%) as driven by mix differences — Power Transmission integration plus broader industrial-end-market exposure (oil-and-gas, mining, aerospace pass-through) that command pricing power and weaker exposure to automotive tier-1 pricing pressure. SKF's existing Connected Technologies platform, aftermarket revenue lines, and the planned 2026 Automotive separation together provide the structural mix-shift pathway — *the planned 2026 separation is the single largest structural mix-shift event* SKF has executed since the 2011 acquisition of Lincoln, and it materially changes the FY2027+ Industrial-only run-rate. The MSEK 3.1B working capital release at 120-day interim parity (R2), scaling to MSEK 7.4B at 95-day Timken-parity stretch over the longer horizon, together with the rightsizing savings flowing from R1 create capital headroom for organic or inorganic investment in this mix shift without exceeding peer leverage norms.

**[LLM]**: **The LLM did not identify mix shift as a strategic lever.** The spec did not contain segment-level revenue or margin detail, so the LLM could not have inferred this lever from the workbook alone. SKF's Connected Technologies and aftermarket-services strategy is publicly disclosed by management and pre-dates this analysis; **author frames it in peer-relative structural-gap terms** by synthesising the peer-benchmark finding (American peers' margin premium reflects mix differences) with SKF's existing strategic platform. This is the longest-horizon and lowest-confidence recommendation in the set — it depends on execution capability the ratio analysis cannot assess — but it is the only recommendation that addresses the *durability* of the post-rightsizing margin expansion rather than its one-time delivery.

---

## 9. Executive Justification — Author Voice

To the CFO and executive committee: **the FY2025 numbers are bad for the right reason** — a disclosed, discrete restructuring program absorbing more than two billion SEK of cost normalisation in a single year. The reported P&L makes the year look like a structural deterioration; the underlying business, on the adjusted basis we publish, is roughly where we said it would be. **What I would tell the board**:

- **The economic-value gap is real** — EVA MSEK (1,835) cannot be normalised away by adjusted-figure storytelling alone. We are creating value below cost of capital. The planned 2026 Automotive separation will remove the lower-return Automotive segment from the consolidated entity; combined with operating margin recovery on the Industrial run-rate, this is the credible path to positive EVA. The peer evidence is clear: every bearings firm that generates positive EVA does so through margin and segment mix, not through balance-sheet engineering.
- **The balance sheet has done its job** — leverage, liquidity, deleveraging trajectory are all where they should be. The capital structure is not the bottleneck. We hold the least leverage in the European bearings peer set. Stop optimising the right-hand side of the balance sheet.
- **The single most important communication choice for FY2026** is whether we frame the year as "post-rightsizing recovery on track" or "structural underperformer." The numbers can support either narrative depending on what we deliver in Q1 and Q2. **My recommendation is to anchor on FY2026 reported operating margin ≥ 8.5% as the KPI we commit to publicly** — it bridges reported to adjusted, it answers the H1 hypothesis the analyst community is testing, it places SKF above the entire European/Japanese cohort on reported figures, and it is achievable on the rightsizing-savings trajectory. We should be clear-eyed internally that 8.5% (and even the FY2027 10% exit target) is a *peer-relative outperformance* commitment, not yet an *EVA-neutrality* commitment — clearing the 9.0% WACC requires a reported EBIT margin of ~11.5%, which is a multi-year objective beyond the FY2027 exit as the IAC charges fully normalise.
- **The peer benchmark adds discipline to the recommendations.** Three of the five recommendations above are sharpened by peer evidence — R1 anchors the margin target against the European/Japanese cohort ceiling (~10% pre-tax) and the American premium band (~16–20% pre-tax); R2 anchors the working capital release at peer-parity sizing (MSEK 3.1B interim at 120-day parity, MSEK 7.4B stretch at 95-day Timken parity); R5 frames the structural mix shift as closing the *durable* peer gap, not the cyclical one.

The work in front of us is not analytical. It is delivery on a margin commitment we have already made internally. The ratio analysis confirms it. The peer benchmark anchors it in industry-relative terms. The Stage 5 deliverable hands the executive team a defensible KPI and a five-recommendation execution agenda; the FY2026 reporting cycle hands the test.

---

## Appendix: 30 Ratios with FY2024 Benchmarks

| Category | Ratio | FY2025 | FY2024 | Direction |
|----------|-------|-------:|-------:|-----------|
| Performance | MVA (MSEK) | 56,257 | ~32,556 | Improving |
| Performance | Market-to-Book | 2.01x | ~1.53x | Improving |
| Performance | EVA (MSEK) | (1,835) | ~+330 | Worsening |
| Profitability | ROA | 4.29% | ~6.1% | Worsening |
| Profitability | ROC | 6.63% | ~9.0% | Worsening |
| Profitability | ROE (direct) | 6.86% | 11.7% | Worsening |
| Profitability | ROA [avg] | 4.54% | n/a | — |
| Profitability | ROC [avg] | 6.97% | n/a | — |
| Profitability | ROE [avg] | 7.22% | n/a | — |
| Efficiency | Asset turnover | 0.77x | ~0.83x | Worsening |
| Efficiency | Receivables turnover | 5.52x | ~5.40x | Stable |
| Efficiency | Avg collection period | 66.2 d | ~67.5 d | Stable |
| Efficiency | Inventory turnover | 2.38x | ~2.70x | Worsening |
| Efficiency | Days in inventory | 153.1 d | ~135 d | Worsening (lagged) |
| Efficiency | Profit margin | 4.64% | 7.0% | Worsening |
| Efficiency | Op profit margin (ATOI/Sales) | 5.60% | ~7.7% | Worsening |
| Leverage | LT debt ratio | 20.3% | ~19.9% | Stable |
| Leverage | LT debt-to-equity | 25.5% | ~24.8% | Stable |
| Leverage | Total debt ratio | 47.7% | 48.1% | Improving |
| Leverage | TIE | 5.64x | ~7.0x | Worsening but healthy |
| Leverage | Cash coverage | 9.11x | ~10.3x | Worsening but healthy |
| Leverage | Debt burden | 0.829 | ~0.85 | Stable |
| Leverage | Leverage ratio | 1.91x | 1.93x | Stable |
| Liquidity | NWC to Assets | 26.8% | 25.2% | Improving |
| Liquidity | Current ratio | 2.11x | ~2.00x | Improving |
| Liquidity | Quick ratio | 0.95x | ~0.85x | Improving |
| Liquidity | Cash ratio | 0.35x | ~0.37x | Stable |
| Du Pont | ROA (Du Pont) | 4.29% | n/a | Matches direct ROA |
| Du Pont | ROE (Du Pont) | 6.80% | n/a | 6 bps gap to direct (V9) |
| Performance | Market cap (MSEK) | 111,925 | ~94,525 | Improving |

---

*End of Final Analysis. Word count excluding Appendix: ~4,300. Author: Hai Dang, VEMBA candidate, Head of People Experience, SKF Vietnam. All numerical claims cross-checked against `analysis/validation/2026-05-27-dang-skf-stage5-verification.md`. Peer-relative claims anchored in `deliverables/2026-05-27-dang-skf-peer-benchmark.md`. LLM contribution documented in `deliverables/prompt-log.md` Stage 5 section.*
