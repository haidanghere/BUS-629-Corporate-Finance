---
template: memo
purpose: "Documented response to Stage 2 professor feedback — what was raised, what changed, where it was committed"
audience: Professor Adam Stauffer; Stage 5 grader
fields_required: [title, to, from, date, re, executive_summary, feedback_received, changes_made, evidence, references]
naming_convention: "YYYY-MM-DD-{lastname}-{slug}.md"
courses: [BUS-629]
title: "Stage 2 Feedback Response — AB SKF Memo Revision"
to: "Professor Adam Stauffer"
from: "Hai Dang"
date: 2026-05-27
re: "Documented response to Stage 2 grading feedback"
stage: 2-feedback-response
---

# Stage 2 Feedback Response — AB SKF Memo Revision

**To:** Professor Adam Stauffer
**From:** Hai Dang
**Date:** 2026-05-27
**Re:** Documented response to Stage 2 grading feedback (filed as Stage 5 rubric criterion #5)

---

## Executive Summary

This memo documents how Stage 2 grading feedback was incorporated into a revised company-selection memo. Two issues were raised: (1) only two distinct hypothesis categories were counted versus the 2–3 target, because H1 and H3 both fell in the profitability category; and (2) the memo's prose was ~844 words versus the 400–600 target. Both issues were addressed in a single revision committed on 2026-05-23 (commit `5ea9292`, "Stage 2 revision: fix H3 category, cut word count to 530"). The revised memo at [`docs/decisions/2026-05-18-dang-skf-selection.md`](../decisions/2026-05-18-dang-skf-selection.md) is the version of record. This response is filed in addition to the commit history to provide an explicit audit trail.

---

## Feedback Received

From the Stage 2 grading rubric and instructor comments:

1. **Hypothesis category overlap.** H1 ("Automotive divestiture explains margin improvement") and H3 ("adjusted ROCE is closer to the 14% target than reported ROCE") both fell within the profitability category. The grading rubric requested 2–3 *distinct* category hypotheses; my submission contained 2 unique categories despite 3 hypothesis numbered items.
2. **Word count overrun.** Prose body of the memo was ~844 words against the 400–600 target. Source: repetition between Executive Summary and Background, expansive Method source detail, and a Findings section longer than necessary for the analytical content delivered.

---

## Changes Made (Commit `5ea9292`, 2026-05-23)

**Change 1 — H3 reframed into Returns on Capital category.** Original H3 ("adjusted ROCE is closer to target than reported ROCE") was reframed to a directional Returns on Capital hypothesis: *"I expect ROCE to recover toward SKF's 14% long-term target by 2025 because the Automotive divestiture removes low-return capital from the employed base."* This is now distinct from H1 (profitability margins) and includes an explicit decomposition test (margin EBIT/Sales versus capital turn Sales/Capital Employed) and a falsifiability condition ("If ROCE fails to recover despite the divestiture, it would suggest the remaining Industrial business carries structural capital inefficiency"). Author decision: revise H3 rather than add a fourth hypothesis, because the rubric target is 2–3, and the goal was to fix category overlap, not expand scope.

**Change 2 — Prose cut from ~844 to ~530 words.** Specific cuts: (a) the Executive Summary no longer repeats Background; (b) Method section condensed — kept the data sources but removed the source-by-source justification; (c) Implications shortened from a paragraph per implication to one paragraph total; (d) Limitations & Next Steps tightened. The financial summary table (FY2021–FY2025) was already moved to `data/skf-financial-summary-2021-2025.md` in the original submission and was not re-counted in the prose word count.

---

## Evidence

| Artefact | Location | What it shows |
|----------|----------|---------------|
| Revised memo | [`docs/decisions/2026-05-18-dang-skf-selection.md`](../decisions/2026-05-18-dang-skf-selection.md) | Current version, 530 words, H1/H2/H3 in three distinct categories |
| Commit | `5ea9292` — "Stage 2 revision: fix H3 category, cut word count to 530" | Git history of the change |
| Prompt log entries | [`deliverables/prompt-log.md`](../../deliverables/prompt-log.md) — Stage 2 Revision section (Prompts 9–11) | LLM-assisted diagnosis and rewrite documented |
| Five-year source data | [`data/skf-financial-summary-2021-2025.md`](../../data/skf-financial-summary-2021-2025.md) | Numerical basis underlying H1/H2/H3 |

---

## Verdict on the Revision

Both feedback items closed:

- **H1/H2/H3 are now in three distinct categories** — H1 profitability margin recovery, H2 leverage/deleveraging path, H3 Returns on Capital (ROCE). No category overlap.
- **Prose word count 530, within 400–600 target** — verified by manual count of the body sections (Executive Summary + Background + Method + Findings + Implications + Limitations & Next Steps; excluding YAML frontmatter, title, references, and the separate financial summary file).

No disagreement with feedback was raised at submission; revision was treated as a straightforward fix of two specific, well-formed criticisms.

---

## References

- Stage 2 brief: https://github.com/adamwstauffer/shidler/blob/main/courses/BUS-629-VEMBA-International-Corporate-Finance/stage2-company-selection.md
- Memo template: https://raw.githubusercontent.com/adamwstauffer/shidler/main/docs/templates/memo-template.md
- Git history: `git log --oneline` — commit `5ea9292`
