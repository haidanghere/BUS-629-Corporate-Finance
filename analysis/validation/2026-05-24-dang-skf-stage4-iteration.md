# Stage 4 — Human-in-the-Loop Iteration Evidence

**Student:** Hai Dang (VEMBA)
**Company:** AB SKF (SKFB.ST)
**Date of iteration:** 2026-05-24
**Spec file:** `docs/specs/2026-05-24-dang-skf-spec.md` (v2.0)

---

## Iteration Framework

This document records the **Round 1 → Round 2** revision of the Stage 4 technical specification. The iteration was driven by self-auditing my v1.0 draft against three reference frames: (1) the Stage 4 rubric items, (2) BUS-629 master template conventions, and (3) general technical-specification quality principles from FP&A practice (named-range discipline, validation harnesses, hypothesis verdict frameworks).

---

## Round 1: Initial Spec (v1.0)

**Prompt submitted to LLM (Claude Code, Sonnet 4.6):**

> Read the Stage 4 brief and spec template at the URLs above. Then, using the spec template's structure, draft a technical specification for SKF accounting ratios analysis.
>
> Requirements:
> - Populate every section (Part A items 1–7, Part B items 8–11)
> - Use named-range notation (BAL_*, INC_*, CASH_*, RATIO_*) throughout
> - Where data values appear in my uploaded Stage 3 workbook, include them numerically in the Data Inputs table
> - Keep the YAML frontmatter from the template intact
>
> Before drafting, list the three or four assumptions you'll need from me.

**Assumptions confirmed before drafting:**
1. Reporting standard + currency: IFRS (EU) / MSEK
2. Audience: AB SKF CFO + executive committee
3. Cost of capital: 9.0% class default
4. Peer set: Schaeffler, NSK, NTN, Timken (4 global bearing peers)

**v1.0 Output:** Complete 11-section spec with all rubric-required components. ~3,000 words.

---

## Gap Analysis (between Round 1 and Round 2)

Before publishing v1.0, I read through the draft as if I were the Stage 5 LLM consuming it cold — looking for ambiguity, missing structure, and places where the spec described *what* the model contained without telling Stage 5 *how to interpret* it. Six specific gaps surfaced.

### Gap 1: No Interpretation Guide

**Symptom in v1.0:** §6 listed all 30 ratios with formulas and values, but a Stage 5 LLM has no way to know whether `EVA = (1,835)` is good, bad, or neutral without an external benchmark. The spec assumes Stage 5 knows industrial-sector norms; that's an unsafe assumption for a cold-context consumer.

**Fix in v2.0:** Added §6g — a table with 6 categories × 3 columns showing what "High" signals, what "Low" signals, and where SKF's FY2025 reading sits. This converts every ratio in §6 into an interpretable signal rather than a raw number.

### Gap 2: No Hypothesis Evaluation framework

**Symptom in v1.0:** Stage 2 specified three hypotheses (H1 profitability recovery, H2 leverage manageable, H3 ROCE recovery via Automotive exit), but v1.0 gave Stage 5 no instructions on how to deliver a verdict. The analysis would risk being narrative without explicit pass/fail criteria.

**Fix in v2.0:** Added §8b with CONFIRMED / REJECTED / INCONCLUSIVE verdict framework. For H3, I went stricter than a binary test: CONFIRMED only if Du Pont decomposition shows **BOTH** margin (EBIT/Sales) AND capital turn (Sales/Capital Employed) improved post-divestiture. This forces Stage 5 to do real decomposition work — single-component improvement is not sufficient evidence given the Stage 2 mechanism (Automotive exit lifts both margin AND capital efficiency).

### Gap 3: No Trend Commentary requirement

**Symptom in v1.0:** §8 referenced YoY benchmarks vaguely. Stage 5 could comply by mentioning one or two ratios in passing.

**Fix in v2.0:** Added §8c with explicit count and structure: compare FY2025 vs FY2024 for **≥6 ratios**; identify **2 most significant improvements** + **1 most significant concern**; each backed by ratio value + 1-sentence business explanation.

### Gap 4: Only 6 validation rules — insufficient programmatic coverage

**Symptom in v1.0:** Validation V1–V6 covered balance-sheet ties and the Du Pont ROA match. Missing: IS arithmetic (EBIT = Sales − COGS − SG&A − D&A), Net Income arithmetic (EBT − Taxes), and explicit Du Pont ROE reconciliation. Stage 5 could miss a model-input error and still produce a "passing" analysis.

**Fix in v2.0:** Expanded to V1–V9. V9 specifically reframes the Du Pont ROE (6.80%) vs direct ROE (6.86%) gap (6 bps) as an **acceptable structural denominator mismatch**, not a data error — because Du Pont leverage uses current-year balances while asset turnover uses prior-year assets. Stage 5 must surface this as a transparency note in narrative.

### Gap 5: No named-range column in §3 Data Inputs

**Symptom in v1.0:** §3 tables listed line items and values but not the named ranges. Stage 5 had to cross-reference §4 conventions back to §3 every time it wanted to use a value in a formula — fragile and error-prone.

**Fix in v2.0:** Added a `Named Range` column to every sub-table in §3 (3a IS, 3b BS current, 3c BS prior, 3d CF, 3e Assumptions). Each line item now resolves to a single canonical named range in one lookup. ~65 named ranges enumerated.

### Gap 6: No structured recommendation framework

**Symptom in v1.0:** §10 listed suggested themes for recommendations but gave Stage 5 no required structure. Recommendations risked being a list of opinions rather than a defensible analytical position.

**Fix in v2.0:** Restructured §10 to a 5-element decision frame: (1) one-sentence thesis (BUY/HOLD/CAUTIOUS HOLD), (2) cite ≥3 ratio findings as evidence, (3) identify 1 material risk, (4) connect to Stage 2 hypothesis verdict from §8b, (5) forward-looking KPI to monitor in FY2026. Each recommendation must also satisfy: evidence-based + quantified (bps/MSEK) + actionable lever + time-bound.

---

## Round 2: Differentiated Insight Added (v2.0)

After closing the six structural gaps, I added five upgrades that go beyond rubric-minimum and represent the analytical depth I want Stage 5 to deliver.

### Upgrade A: Du Pont counterfactual quantification (§9)

The decomposition alone tells Stage 5 *what* the components are; the counterfactual tells it *what's possible*. Added: *"If margin → 10% (peer median): ROE → 1.91 × 0.77 × 10% × 0.829 = 12.2% (+540 bps)."* This frames operating margin as the single highest-leverage improvement lever.

### Upgrade B: Peer benchmark set named (§8a)

Named four global bearing peers explicitly: Schaeffler (SHA.DE), NSK (6471.T), NTN (6472.T), Timken (TKR). Stage 5 now has a defined comparison set rather than abstract "industry benchmarks."

### Upgrade C: Cross-category connections explicit (§8a)

Pre-specified four required analytical connections (profit↔efficiency, profit↔performance, leverage↔profit, Automotive divestiture FY2026 impact). Without this, Stage 5 might produce a category-by-category analysis without integrating insights across categories — a common weakness in ratio analysis.

### Upgrade D: §12 Sensitivity Specification (portfolio extension)

The headline finding is **EVA = (1,835) MSEK**. This is mechanically the consequence of ROC (6.63%) < WACC (9.0%). But the 9.0% is a class assumption, not SKF's actual WACC. A defensible analysis must address: *how robust is "negative EVA" to reasonable variation in WACC?*

Added §12 with: `cost_capital` range 7.0–11.0% (triangular, mode 9.0%), `tax_rate` range 30.0–37.0% (uniform); required outputs include tornado chart (Excel native), 5,000-trial Monte Carlo P10/P50/P90 (Python numpy or @RISK), and the breakeven-WACC narrative. Pre-computed answer: **EVA crosses zero at cost_capital = 6.63%** (which equals ROC). This converts a point-estimate analysis into an uncertainty-aware analysis.

### Upgrade E: Revision Log table

Added per industry-standard spec practice. Tracks v1.0 → v2.0 changes so a reader (instructor, peer reviewer, or a future me) can audit the iteration history.

---

## Self-Containment Test (Stage 4 Quality Bar)

After v2.0 edits, the spec was re-read as if by a fresh LLM with no prior context. Test questions answered from spec text alone:

| Question | Section | Pass |
|----------|---------|------|
| What is FY2025 EVA and why? | §6a + §6g | ✓ −1,835 MSEK; ROC 6.63% < WACC 9.0% |
| Which BS date for ROA denominator? | §6b | ✓ `startYear_total_assets` (FY2024) |
| What is the Du Pont ROE formula and value? | §6f | ✓ 1.91 × 0.77 × 5.60% × 0.829 = 6.80% |
| Why is direct ROE ≠ Du Pont ROE? | §6f + V9 | ✓ Denominator time-mismatch; 6 bps gap acceptable |
| How is H3 evaluated? | §8b | ✓ CONFIRMED requires BOTH margin AND capital turn improvement |
| What length should Stage 5 deliver? | §11 | ✓ 1,500–2,500 words excl. Appendix |
| What does "EVA crosses zero" mean? | §12 | ✓ At cost_capital = 6.63% = ROC |
| What named range = `currentYear_after_tax_operating_income`? | §5 | ✓ `INC_net + (1 − tax_rate) × INC_interest_expense` = 5,128 |

**Spec passes self-containment.**

---

## Reflection: What this iteration changed about my drafting process

The Round 1 → Round 2 jump was not about adding more content — it was about **separating structural rigor from analytical depth**, then doing both. v1.0 had most of the analytical depth but missed structural conventions (verdict framework, interpretation table, named-range column). v2.0 closed those structural gaps first, then layered on differentiated insight (counterfactual, peer set, sensitivity).

The lesson for future spec work: **structure first, insight second**. Adding novel insight on top of a structurally weak draft compounds the wrong way; closing structural gaps first then adding insight compounds the right way.

The single highest-leverage change was Gap 4 (validation rules V1–V9). Adding explicit pass conditions to each check turned the spec from a description of what the model does into a programmatic conformance test — Stage 5 can now verify the model before writing narrative, not after.

---

## Counterfactual: "What prompt should I have used if starting cold?"

The actual prompts I used (recorded in the prompt log) leveraged existing session context — Stage 3 workbook already loaded, Stage 2 hypotheses known, BUS-629 template conventions internalized. Writing the prompt I would have used in a clean session is a useful methodology artifact:

```
Using the attached Stage 4 brief, spec template, Stage 1 memo, and 
Stage 3 populated workbook, draft a complete 12-section technical 
specification for AB SKF (SKFB.ST) for FY2025 under IFRS. Use named-
range notation throughout. For each ratio in §6, include the formula, 
the expected FY2025 value, and the unit. Include validation rules 
V1–V9 with explicit pass conditions. Map Stage 2 hypotheses H1/H2/H3 
to §8b verdict criteria using CONFIRMED/REJECTED/INCONCLUSIVE; for 
H3, require Du Pont to show BOTH margin AND capital turn improvement 
before issuing CONFIRMED verdict. Include §12 sensitivity covering 
cost_capital (7-11%) and tax_rate (30-37%) with tornado, Monte Carlo 
(P10/P50/P90), and breakeven-WACC narrative. Target 2,000–2,500 words.

Before drafting, ask 3–4 clarifying questions about reporting standard, 
audience, cost of capital assumption, and peer set.

Use data values from the Stage 3 workbook directly — do not look them 
up externally.
```

Writing this retrospectively closes the methodology loop and makes the spec reproducible from a clean session — which is the standard the spec must meet for Stage 5 execution.

---

*End of HIL iteration document. Submitted as Stage 4 rubric criterion #4 (Spec craft + prompt log + HIL iteration).*
