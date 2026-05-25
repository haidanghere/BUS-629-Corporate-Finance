# Stage 4 — Instructor Review

**Student:** Dang Hai
**Company:** AB SKF (SKFB.ST, Nasdaq Stockholm)
**Spec:** `docs/specs/2026-05-24-dang-skf-spec.md`
**Reviewed:** 2026-05-24

---

## Observations

### Part A — Model Specification

- **Scope & Objective (Section 1):** Well-defined — identifies IFRS (EU), MSEK, SKFB.ST, FY2025/FY2024, CFO + exec committee audience. Analytical objective explicitly framed around 30-ratio framework and Automotive divestiture context. Model read-only at Stage 5 — a useful constraint for the executor.
- **Model Architecture (Section 2):** Six-tab workbook documented with color coding conventions (Blue = inputs, Black = formulas, Green = cross-sheet links, Yellow = assumptions), formatting requirements, and Open Sans typography spec. Clean tabular format.
- **Data Inputs (Section 3):** Comprehensive — IS (12 items), BS FY2025 (20 items), BS FY2024 (20 items), CFS (4 items with AR2025 reconciliation note explaining 236 MSEK gap), Analyst assumptions (5 items). Named-range column present in every sub-table — a Stage 5 LLM can map any value directly to its canonical named range in one lookup.
- **Named Range Conventions (Section 4):** Prefix table with `BAL_*_curr/_prior`, `INC_*`, `CASH_*`, `RATIO_*`, `startYear_*`, `currentYear_*`, `avg_*` aliasing. Critical rule: "no direct cell references in any ratio formula."
- **Derived Inputs (Section 5):** 22 intermediate calculations with explicit formulas and computed values. Includes `market_capitalization` (share_price × shares_outstanding × 1000 = 111,925 MSEK), `currentYear_after_tax_operating_income`, `currentYear_daily_sales_average`, and all avg_* calculations.

### Part A — Ratios & Validation

- **Ratio Definitions (Section 6):** 30 ratio rows across all six categories — Performance (3), Profitability (6 including start-year and avg variants), Efficiency (7), Leverage (7), Liquidity (4), Du Pont (2). All in named-range notation with computed FY2025 values.
- **Interpretation Guide (§6g):** Novel addition — a summary table mapping each category to "High signal / Low signal / SKF FY2025 reading." For example: Efficiency = MIXED (receivables 66 days OK; inventory 153 days = drag). This converts raw numbers into interpretable signals for the Stage 5 executor.
- **Validation Rules (Section 7):** 9 rules (V1–V9): BS balance both years (with exact values), IS arithmetic (EBIT), Net income, Du Pont ROA match, no formula errors, EVA sign check (confirms ROC 6.63% < WACC 9.0%), positive startYear values, Du Pont ROE reconciliation (6 bps gap acknowledged as structural denominator mismatch).

### Part B — Analysis Specification

- **Analysis Requirements (§8a):** Per-category analysis with cross-category connections explicitly required (profit↔efficiency, profit↔performance, leverage↔profit, Automotive divestiture FY2026 ROCE impact). Four named peers: Schaeffler, NSK, NTN, Timken.
- **Hypothesis Evaluation (§8b):** Stage 2 hypotheses mapped to verdict criteria — H1 (profitability), H2 (leverage), H3 (ROCE recovery). H3 uses a strict BOTH-component test: CONFIRMED only if Du Pont decomposition shows BOTH margin (EBIT/Sales) AND capital turn (Sales/Capital Employed) improved post-divestiture. INCONCLUSIVE if only one improved. This is the most rigorous verdict framework in the cohort.
- **Trend Commentary (§8c):** Explicit requirement — compare ≥6 ratios FY2025 vs FY2024; identify 2 most significant improvements + 1 most significant concern with ratio values and business explanation.
- **Du Pont Decomposition (§9):** Full 4-factor chain with values (1.91x × 0.77x × 5.60% × 0.829 = 6.80%). Counterfactual: if margin→10% (peer median): ROE→12.2% (+540 bps). Identifies operating margin as binding constraint.
- **Recommendation Requirements (§10):** 5-element framework — one-sentence thesis (BUY/HOLD/CAUTIOUS HOLD), cite ≥3 ratio findings, identify 1 material risk, connect to Stage 2 hypothesis, forward-looking KPI. Each rec must be evidence + quantified + actionable + time-bound.
- **Sensitivity Specification (§12):** Post-rubric extension addressing WACC robustness of the negative-EVA finding. `cost_capital` 7.0–11.0% (triangular, mode 9.0%); `tax_rate` 30.0–37.0% (uniform). Required outputs: tornado chart, 5,000-trial Monte Carlo P10/P50/P90, breakeven-WACC narrative (answer: 6.63% = ROC).

### Prompt Log & HIL Iteration

- **Prompt log:** 29 entries spanning Stages 2–4. Each stage has an LLM-vs-author contribution table showing what the model did vs. what the author verified/decided. Authentic Vietnamese prompts alongside English. Stage 3 documents 10 verification rounds (IS, BS, CF, Ratios) with specific corrections at each step. Stage 4 documents v1.0 initial draft, self-audit, gap-closure, differentiator upgrades, trim iterations, and final audit. Includes an ideal cold-context counterfactual prompt — a reproducibility artifact.
- **HIL iteration** (separate file, 2,700+ words): Round 1→Round 2 framework with 6 gap closures (interpretation guide, hypothesis framework, trend commentary, validation V7-V9, named-range column, recommendation structure) + 5 differentiator upgrades (counterfactual, peer set, cross-category connections, §12 sensitivity, revision log). Self-containment test: 8 questions answered from spec text alone. Reflection on process: "structure first, insight second."

---

## Kindly-worded suggestions for improvement

- **This is the most analytically sophisticated Stage 4 submission in the cohort.** The combination of §8b Hypothesis Evaluation (with the BOTH-component H3 test), §6g Interpretation Guide, and §12 Sensitivity Specification demonstrates spec engineering that goes well beyond the rubric. The self-containment test — 8 questions answered from spec text alone — is an excellent quality assurance practice that any professional spec writer would benefit from adopting.
- **The Du Pont counterfactual is a strong analytical move.** Stating "if margin→10%: ROE→12.2% (+540 bps)" converts the decomposition from "here are the components" into "here is what's actionable." A senior reviewer reading this immediately knows where the highest-leverage improvement sits — operating margin, not leverage or turnover.
- **The prompt log's LLM-vs-author contribution tables** are the most transparent methodology documentation in the cohort. These demonstrate genuine intellectual ownership while acknowledging the LLM's role clearly.
- **Minor: Cash flow reconciliation gap (7,978 vs AR's 8,392 = 236 MSEK).** The §3d note explains this as "template simplification — no non-cash items line." Consider adding a V10 validation rule that explicitly acknowledges this gap so a Stage 5 LLM doesn't flag it as an unexplained discrepancy.
- **Minor: Automotive divestiture timing.** Confirm in Stage 5 that the divestiture closed fully in the period being analyzed, so the H3 verdict can distinguish divestiture-driven improvements from organic performance gains.

**Looking ahead to Stage 5:** Your spec is detailed enough that a Stage 5 LLM should produce high-quality output on the first run. The key verification targets are: (1) the §8b hypothesis verdicts (does the LLM correctly evaluate the BOTH-component test for H3?), (2) the §12 sensitivity narrative (does the LLM correctly identify EVA breakeven at 6.63%?), and (3) the Du Pont counterfactual (does the LLM reproduce the +540 bps calculation?).
