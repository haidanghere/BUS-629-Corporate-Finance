---
template: stage5-spec-retrospective
purpose: "Self-evaluation of the Stage 4 spec based on Stage 5 execution evidence — what worked, what didn't, what I'd change"
audience: Stage 5 grader; future self if I draft another technical spec
stage: 5
author: Hai Dang (VEMBA)
date: 2026-05-27
company: AB SKF
ticker: SKFB.ST
spec_under_review: docs/specs/2026-05-24-dang-skf-spec.md v2.0
evidence_basis:
  - deliverables/2026-05-27-dang-skf-llm-raw.md (Stage 5 LLM raw output)
  - analysis/validation/2026-05-27-dang-skf-stage5-verification.md (manual verification)
  - deliverables/2026-05-27-dang-skf-final-analysis.md (final analysis with author corrections)
---

# Stage 4 Spec Retrospective — AB SKF Ratio Analysis
**Stage 5 deliverable · BUS-629 VEMBA · Hai Dang**

The spec under review is the v2.0 self-iterated draft I published on 2026-05-24 with the goal that a cold-context Stage 5 LLM would produce a substantially correct analysis from spec text alone. This retrospective evaluates how that goal was met, where it fell short, and what I would change.

---

## 1. Section-by-Section Verdict

Verdicts: **Clear** (LLM produced expected output), **Vague** (LLM had to make a judgment call), **Missing** (analytical gap surfaced in Stage 5).

| Section | Verdict | Symptom in Stage 5 output |
|---------|---------|---------------------------|
| §1 Scope & Objective | **Clear** | LLM correctly identified subject, period, audience, and analytical centre (FY2025 + Automotive divestiture frame). |
| §2 Model Architecture | **Clear** | Tab structure, color convention, format conventions ingested cleanly. No symptom. |
| §3 Data Inputs | **Clear** with one defect | All 22 BS lines, 12 IS lines, 10 CF lines, 22 derived inputs flowed into ratio calcs without error. **Defect**: §3e market-cap input units (M = millions) inconsistent with §5 formula (`× 1000`) — see Gap 2 below. |
| §4 Named Range Conventions | **Clear** | Prefix discipline (`BAL_*_curr/_prior`, `INC_*`, `startYear_*`, `currentYear_*`, `avg_*`) held across LLM output. No named-range collisions or misreads. This was the strongest section. |
| §5 Derived Inputs | **Clear** with one defect | All 22 derived values reproduced. **Defect**: `market_capitalization` formula `share_price × shares_outstanding × 1000` produces 111,925,030 if read literally with shares-in-millions input (455.35), but spec result row shows 111,925. The "×1000" is wrong notation. — see Gap 2. |
| §6 Ratio Definitions | **Mostly Clear** | All 30 ratios computed correctly per spec convention. **Minor naming issue**: §6c labels `RATIO_operating_profit_margin = currentYear_after_tax_operating_income / INC_sales` as "Operating profit margin." This is **after-tax operating margin (ATOI/Sales)**, not the conventional EBIT/Sales. A cold LLM correctly executed the formula but a CFO reader unfamiliar with the spec convention could read 5.60% as EBIT margin and conclude SKF is in worse shape than reported EBIT/Sales 8.19% indicates. — see Gap 3. |
| §6g Interpretation Guide | **Clear** | LLM applied LOW/MIXED/HEALTHY/STRONG labels correctly per the spec table. This was a high-leverage v2.0 addition. |
| §7 Validation Rules V1–V9 | **Clear** | All 9 checks executed. V9 (Du Pont vs direct ROE reconciliation) caught a known artefact. **Minor**: V9 told LLM the gap is acceptable but did not instruct on which figure to *cite* — see Gap 1 below. |
| §8a Analysis Requirements | **Clear** | Cross-category connections pre-specified; LLM produced integrated analysis rather than category-by-category. |
| §8b Hypothesis Evaluation | **Vague on adjusted vs reported** | LLM ran H1/H2/H3 verdict tests on reported figures correctly. **But** the verdict differs sharply if run on adjusted figures (SKF's published APM disclosures: H1 CONFIRMED, H3 CONFIRMED). Spec said nothing about this dual-basis test. — Gap 1 (most consequential). |
| §8c Trend Commentary | **Clear** | 6+ ratio YoY comparison + 2 improvements + 1 concern structure delivered as specified. |
| §9 Du Pont Decomposition | **Clear** | Counterfactual reproduced (+540 bps to ROE if margin → 10%). |
| §10 Strategic Recommendations | **Clear** | 5-element decision frame applied — but spec did not require dividend-policy connection, which is the single most important capital-allocation question for a CFO audience. The LLM did not address it. Not strictly a spec failure since §10 did not require it; arguably a *vague* on audience-fit. |
| §11 Output Format | **Clear** | Word band 1,500–2,500 honoured; structure followed. |
| §12 Sensitivity Spec | **Vague on execution** | Spec required tornado + 5,000-trial Monte Carlo + breakeven narrative. LLM produced indicative P10/P50/P90 without running the simulation, plus the algebraic breakeven (6.63%). The spec did not specify what to do if the LLM lacked a simulation tool. — Gap 3 (deferred to forward link). |

**Summary count**: 12 Clear, 3 Vague (§8b reported-vs-adjusted, §10 dividend-policy audience-fit, §12 simulation executability). 0 Missing — every required component was in the spec; the issues are about depth and execution path, not omission.

---

## 2. Top Three Gaps with Evidence

### Gap 1 — Reported vs adjusted figures dual-basis test (most consequential)

**Where it appeared in Stage 5 output**: §4 of Final Analysis (Hypothesis Evaluation). LLM raw output marked H1 as REJECTED and H3 as INCONCLUSIVE on reported figures. The author overlay flipped both verdicts toward CONFIRMED when adjusted figures are applied. The reader of the LLM raw output alone — a hypothetical Stage 5 grader who reads only that file — would conclude SKF's recovery hypotheses had failed; the reader who looked further would learn they had not.

**What caused it**: Spec §8b prescribed test criteria using reported-figure named ranges only (`INC_ebit`, `INC_net`, etc.). The spec did not state what to do with adjusted figures, and the Stage 3 workbook did not contain them. The LLM did exactly what the spec required and produced a literally-correct but analytically-incomplete verdict.

**Exact spec language I would add** (proposed §8b insertion):

> **§8b.2 — Dual-basis verdict.** Each hypothesis verdict must be issued twice: once on reported figures (spec §3 named ranges) and once on the adjusted-operating-margin basis published by SKF in APM disclosures (`adj_operating_margin` named range to be added to §3e at value 12.7% for FY2025, 12.3% for FY2024; `adj_roce` at 14.3% FY2025, 14.2% FY2024). Where the two bases disagree, the spec requires the LLM to identify the source of disagreement (typically IAC) and quote both verdicts; the strategic recommendation must commit to one verdict with explicit reasoning.

### Gap 2 — Market capitalization formula notation defect

**Where it appeared in Stage 5 output**: Verification table row R9. Spec §5 formula `share_price × shares_outstanding × 1000` produces 111,925,030 if read literally with shares stated in millions (455.35), but the result row shows 111,925. The LLM produced the correct answer 111,925 by inferring intent, not by following the formula.

**What caused it**: Inconsistency between §3e (which states shares_outstanding in millions: "Basic = diluted (M) | 455.35") and §5 (which applies a "× 1000" multiplier as if shares were in billions). The two sub-sections were edited at different times during the v1.0→v2.0 iteration and not reconciled.

**Exact spec language I would add** (proposed §5 fix):

> `market_capitalization` = `share_price × shares_outstanding` (where `shares_outstanding` is in millions and `share_price` is in SEK; product is MSEK directly — no scaling required). FY2025 value: 245.80 × 455.35 = **MSEK 111,925**.

Drop the "× 1000" entirely.

### Gap 3 — §12 Sensitivity executability (Monte Carlo tooling)

**Where it appeared in Stage 5 output**: §7 of Final Analysis. The LLM did not run the 5,000-trial Monte Carlo because no simulation tool was specified inside the workbook; it produced indicative P10/P50/P90 figures labelled "estimated." The author override replaced these with the algebraic breakeven analysis (EVA = 0 at `cost_capital` = ROC = 6.63%), which is more diagnostic and reproducible from the spec alone.

**What caused it**: Spec §12 specified the simulation design (distributions, trial count, deliverables) but located the execution tooling outside the spec ("Python (numpy + matplotlib) or Excel @RISK add-in"). A cold-context LLM with no execution environment will skip the simulation step.

**Exact spec language I would add** (proposed §12 fix):

> **§12.2 — Algebraic breakeven first; simulation second.** Required output 1: algebraic breakeven WACC at which EVA = 0 (here: 6.63%, identically ROC). Required output 2 (conditional): 5,000-trial Monte Carlo P10/P50/P90, **only if a simulation environment is available**; otherwise, narrative robustness statement based on the breakeven WACC and the upper/lower bounds of the distribution. Indicative or simulated P10/P50/P90 figures **must be labelled** as such; never present indicative figures without disclosure.

---

## 3. Three Revisions if Re-Running (Numbered to Gaps)

**Revision 1 (Gap 1, highest impact)**: Add §8b.2 Dual-basis verdict requirement. Add `adj_operating_margin` and `adj_roce` to §3e Analyst Assumptions with values pulled from SKF's APM disclosure (12.7%/14.3% FY2025; 12.3%/14.2% FY2024). Expected impact: H1 and H3 verdicts become CONFIRMED on adjusted basis; the analytical narrative becomes the "reported-vs-adjusted bridge" story that is the actual investor question, not a literally-correct but incomplete reported-only test.

**Revision 2 (Gap 2)**: Fix §5 `market_capitalization` formula. Drop "× 1000"; restate units explicitly. Reconcile against §3e shares_outstanding line. Expected impact: zero analytical change (output value unaffected), but removes a clean correctness defect a sceptical reviewer would catch.

**Revision 3 (Gap 3)**: Add §12.2 — Algebraic breakeven before simulation; explicit handling for missing simulation tooling. Expected impact: even a cold LLM with no tools produces a defensible sensitivity output (the algebraic breakeven), and any simulated MC is disclosed-as-such rather than presented as if executed.

---

## 4. Effectiveness Rating: 4 / 5

**Anchor**:
- **5/5 ("polished CFO product")** would mean a cold-context LLM produces a complete analysis requiring zero author override on framing or numerical correction. My spec produced minor numerical artefacts (R8 chained Du Pont) and one analytical gap (H1/H3 reported-vs-adjusted) that required author override.
- **4/5 ("publishable working draft")** means a cold LLM produces ~80% of the final analysis correctly; the author closes 1–2 substantive gaps and 1–2 numerical-cleanup items. **This is where I land.**
- **3/5 ("usable starting point")** would require ≥50% author rewrite. The spec was substantially better than this.
- **1–2/5** would mean the LLM produced an unusable output. Not the case.

**Justification**: 12 of 15 sections produced Clear LLM output; the three Vague items required author judgment but did not invalidate the analysis. The structural rigor added in v2.0 (interpretation guide §6g, hypothesis verdict framework §8b, validation expansion V1–V9, named-range column in §3) is what kept this at 4/5 — without those, the spec would have been closer to 3/5. The 1-point deduction is split across (i) Gap 1 reported-vs-adjusted (the most important analytical addition the author had to make), (ii) Gap 2 market-cap formula notation, and (iii) Gap 3 simulation executability.

---

## 5. Forward Link

**Next spec approach**: For any future spec where the company publishes both reported and management-adjusted financial measures (which is most large industrials), bake the reported-vs-adjusted bridge into the spec as a required output section — not a footnote, not an analyst override.

---

## 6. Process Feedback on the Template (≤150 words)

The spec template's strongest feature is the named-range discipline (Part A §3–§5). Its weakest is that it treats the spec as a static contract between author and Stage 5 LLM, without an explicit mechanism for **versioned assumption overlays** — e.g. reported vs adjusted, current accounting period vs prior, base case vs sensitivity. In practice, the analytical question is almost always *"how does the answer change under assumption X vs Y?"*, and the template forces this work into ad-hoc §12-style extensions.

**Structural suggestion**: Add a Part B §8d "Assumption Overlay Table" required section, where the author lists pairs of assumption sets (e.g. reported/adjusted, FY2024-base/FY2025-base, WACC=class-default/WACC=actual) and specifies how the analysis should treat each pair. This converts the verdict framework (§8b) from a single-basis test into a multi-basis test by default — which is how real CFO-grade analysis is done. (146 words.)

---

*End of Spec Retrospective. Evidence ties to verification table (R8, R9), final analysis (§4, §7, §8), and the raw LLM output (Hypothesis Evaluation, Sensitivity sections).*
