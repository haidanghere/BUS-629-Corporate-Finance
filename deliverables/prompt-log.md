# Prompt Log — BUS 629 Corporate Finance Project

This file logs all substantive AI-assisted prompting used in this project, per Stage 2 instructions. Entries are added as work progresses through each stage.

---

## Stage 2 — Company Selection Memo

**Tool:** Claude (claude.ai desktop app / Claude Code)
**Date:** 2026-05-19
**Purpose:** Draft and iterate the Stage 2 company selection memo for AB SKF

### Prompt sequence

**Prompt 1 — Initial draft**
> Read the Stage 2 brief at [URL]. Draft a company selection memo for AB SKF (SKFB: Nasdaq Stockholm). I am Head of People Experience at SKF Vietnam. Use the memo template, YAML frontmatter intact. Length 400–600 words. Audience: Professor Adam Stauffer, managing director tone.

**Prompt 2 — Data grounding**
> The memo references 2024 data but SKF's Annual Report 2025 is now available (published March 2026). Update all data references to use 2021–2025 as the analysis window. [Provided PDF links for Annual Reports 2021–2025]

**Prompt 3 — Timeline correction**
> The memo says the Automotive divestiture completed in 2021. Verify this against the actual Annual Reports. [Correction identified: announced June 2022, closed 2023]

**Prompt 4 — Adjusted margin correction**
> SKF's Long-term targets page shows 2021 operating margin as 13.3%, but the memo shows 13.2%. Explain the discrepancy and update the financial summary table to show both reported and adjusted margins.

**Prompt 5 — Final structure**
> The memo is over 600 words including the financial summary tables. Restructure: keep the selection memo at 400–600 words (sections 1–6 only), move the financial data to a separate file at `data/skf-financial-summary-2021-2025.md`.

### LLM contribution vs. author contribution

| LLM did | Author verified / decided |
|---|---|
| Drafted all six memo sections | Selected SKF as the company |
| Identified divestiture timeline error from Annual Reports | Confirmed familiarity with SKF Vietnam context |
| Extracted and organized 5-year financial data from PDFs | Verified key figures against source documents |
| Formatted hypotheses in "I expect X because Y" structure | Chose which hypotheses were analytically interesting |
| Suggested YAML frontmatter structure | Confirmed all submission checklist items |

---

**Prompt 6 — Template compliance audit**
> AUDIT THIS WITH RESULT YOU HAVE DONE: I'm drafting a Stage 2 company selection memo for my finance course. The memo template is at: https://raw.githubusercontent.com/adamwstauffer/shidler/main/docs/templates/memo-template.md — Please read the template, then audit the current memo against it.

**Prompt 7 — Section restructure to match template**
> YES PLEASE [rewrite with correct section headings]

*Outcome:* LLM fetched the live template, identified 5 missing required section headings (`Background`, `Method`, `Findings`, `Implications`, `Limitations & Next Steps`) and 2 YAML deviations (`audience`, `purpose`). Memo rewritten to map all existing content to correct headings and add new `Implications` and `Limitations & Next Steps` sections. All verified SKF data retained unchanged.

---

**Prompt 8 — Findings section review**
> REVIEW THIS: [revised Findings section with richer hypothesis framing, explicit test methodology, and "April 2026 separation" references]

*Outcome:* LLM identified three issues requiring correction before submission: (1) unverified "April 2026 separation" claim removed — not in any Annual Report 2021–2025; (2) Hypothesis 1 logic fixed — framing implied divestiture was still pending when it closed in 2023; (3) Hypothesis 3 accuracy corrected — "remain anchored" overstated, 2022 adjusted ROCE was 12.6% (below 14% target). Analytical upgrades retained: explicit test methodology for each hypothesis, EBITDA-growth-vs-debt-reduction decomposition in H2, falsifiability condition in H3. Author reviewed and approved changes.

---

---

## Stage 2 — Revision (post-professor feedback)

**Tool:** Claude (Claude Code)
**Date:** 2026-05-23
**Purpose:** Revise Stage 2 memo in response to professor feedback: (1) only 2 clean hypotheses counted vs. 2–3 target; (2) prose word count ~844 vs. 400–600 target.

### Prompt sequence

**Prompt 9 — Diagnose feedback**
> [Screenshot of professor feedback] bảng sau là feedback của giáo sư và điểm của stage 2, hãy tìm hiểu nguyên nhân vì sao điểm thấp và cần tìm cách fix nó để submit lại

*Outcome:* LLM identified two root causes: (1) H1 and H3 both fell in the profitability category — professor only counted 2 distinct hypothesis categories; (2) H3 was not falsifiable in a meaningful sense ("adjusted ROCE closer to target than reported ROCE" is true by definition). Word count ~844 exceeded 400–600 target by ~250 words.

**Prompt 10 — H3 reframe decision**
> có thể làm rõ cái H3 thay vì thêm H4 ko

*Outcome:* Author decided to reframe H3 into the Returns on Capital category (distinct from H1's profitability margins) rather than adding a fourth hypothesis. Rationale: professor target is 2–3 hypotheses; current count is already 3; fixing category overlap is sufficient.

**Prompt 11 — Rewrite memo**
> yes pls [confirm rewrite]

*Outcome:* Memo rewritten with two changes: (1) H3 reframed from "adjusted vs. reported ROCE comparison" to a directional Returns on Capital hypothesis — "I expect ROCE to recover toward SKF's 14% target because Automotive exit removes low-return capital from the employed base" — with decomposition test (EBIT/Sales vs. Sales/Capital Employed) and explicit falsifiability condition; (2) prose cut from ~844 to ~530 words by removing repetition between Executive Summary and Background, trimming Method source details, and condensing Implications.

### LLM contribution vs. author contribution (revision)

| LLM did | Author verified / decided |
|---|---|
| Diagnosed why H3 was not counted as a clean hypothesis | Decided to fix H3 rather than add H4 |
| Reframed H3 into Returns on Capital category | Confirmed the business logic (Automotive ROCE < Industrial) |
| Identified repetitive passages causing word count overrun | Approved final word count and content cuts |
| Rewrote memo to ~530 words | Reviewed all retained data for accuracy |

---

*Additional entries will be added for Stages 3–5.*
