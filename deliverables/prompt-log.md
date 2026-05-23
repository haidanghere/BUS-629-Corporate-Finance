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

---

## Stage 3 — Excel Financial Model Population

**Tool:** Claude (Claude Code)
**Date:** 2026-05-23
**Purpose:** Populate the BUS-629 Excel template (`models/builds/2026-05-19-dang-skf-financials.xlsx`) with SKF FY2025 and FY2024 audited financials from the Annual Report 2025. Verify all entries against source, fix formula and data errors, and bring Notes tab to the same standard as peer example.

---

### Prompt sequence

**Prompt 12 — Initial model population**
> @[Excel file path] PLEASE WORK AGAIN ON THIS FILE AS THERE ARE MANY BOX STILL EMPTY

*Outcome:* LLM populated Balance Sheet (assets + liabilities + equity for FY2025/FY2024), Income Statement (revenue through net income), Cash Flow Statement (operating WC items, investing, financing), and Ratios tab (4 assumptions + all 29 ratio formulas using named ranges). File saved to Downloads due to OneDrive reparse-point write block.

---

**Prompt 13 — Shares outstanding unit error**
> @[classmate's Coca-Cola Excel file] here is an example file from my class mate, she choose coca cola

*Outcome:* Comparison revealed shares outstanding entered as 455,351,068 (absolute) instead of 455.35 (millions per template unit). LLM corrected C9 on Ratios tab to 455.35. Market cap formula recalculated correctly: SEK 245.8 × 455.35M = MSEK 111,925.

---

**Prompt 14 — Cash flow depreciation fix**
> vì sao ô plus isse ko có giá trị [screenshot of CF tab showing zero operating CF]

*Outcome:* Root cause identified: Income Statement D&A cell (C9) was 0, so CF formula (Net Income + D&A + WC changes) produced wrong total. Fix: D&A set to 4,624; COGS adjusted from 67,058 to 62,434 (COGS ex-D&A) to maintain correct EBIT. Operating CF corrected from ~3,354 to 7,978.

---

**Prompt 15 — PP&E gross/accumulated depreciation**
> kiểm tra lại hết các chỉ số của balance sheet 1 lần nữa [screenshot showing C14 = 27,785]

*Outcome:* C14 had net PP&E entered as gross PP&E. Corrected: C14 = 66,041 (gross, from Note 11), C15 = 38,256 (accumulated depreciation, from Note 11). Net PP&E formula in C16 auto-calculates to 27,785. Prior year: D14 = 71,970; D15 = 41,500; D16 = 30,470. Both years verified against AR2025 Note 11.

---

**Prompt 16 — Notes tab quality improvement**
> review the note of my classmate compared with my note and give suggestion to get higher quality and grade

*Outcome:* LLM compared SKF Notes tab against Coca-Cola peer example. Identified 8 gaps: missing GICS code, missing fiscal year date ranges, URL-only data source (no access date or secondary sources), missing SEK currency prefix on share price, shares in absolute units instead of millions, missing source citations on tax rate and shares, missing BUS-629 Project Use and Stage 2 Task fields, and incomplete Reporting Standard. All 8 gaps fixed in one pass. Reporting Standard also updated to match peer format.

---

**Prompt 17 — Cash Flow verification vs Annual Report 2025**
> kiểm tra lại chỉ số cashflow statement lại [screenshot of CF tab]

*Outcome:* LLM read AR2025 Consolidated Cash Flow Statement (p. 103). Cross-checked all entries:
- WC items (receivables −805, inventories −549, AP −284, other net +743) confirmed correct from AR.
- "Other current liabilities +1,158" identified as double-count — already captured in "other operating assets/liabilities net +743". Corrected to 0.
- ST debt −4,189 (from BS change): SKF has no separate ST debt line in actual CF; corrected to 0.
- LT debt −4,384: actual = +246 proceeds − 3,729 repayments = −3,483; corrected.
- Other financing −292: actual = leases −901 + post-employment −200 + other +26 + net financial assets −118 = −1,193; corrected.
- Financing CF corrected from −12,478 to −8,289, matching AR exactly.
- Remaining gap in operating CF (7,978 vs actual 8,392): 414 difference is template simplification — no non-cash items line; noted for Stage 4 memo.

---

**Prompt 18 — Income Statement verification**
> please double check the income statement [screenshot]

*Outcome:* All IS lines verified against AR2025 p.99. Key reconciliations: COGS ex-D&A = 67,058 − 4,624 = 62,434 ✓; SG&A = R&D 3,409 + Selling 12,657 + Admin 961 = 17,027 ✓; Other income 257 = net other operating income (3,480−3,284=196) + associates 61 ✓; Net interest 1,330 = financial expenses 1,619 − financial income 289 ✓. No corrections needed.

---

**Prompt 19 — Balance Sheet verification**
> please double check the balance sheet [screenshot]

*Outcome:* All 22 BS line items verified against AR2025 p.101 for both FY2025 and FY2024. Key aggregations confirmed: Other current assets = other ST assets + ST financial assets (5,780+482=6,262); Intangibles = goodwill + other intangibles (10,925+3,487=14,412); Other assets = ROU + LT financial + deferred tax + JV + other LT + assets HFS (9,688+206=9,894); Debt due for repayment = ST financial liabilities + ST lease liabilities (444+728=1,172); LT debt = LT financial liabilities + LT lease liabilities (12,001+2,167=14,168). Total Assets = Total L+E = 106,422 (FY2025) and 119,413 (FY2024). No corrections needed.

---

**Prompt 20 — Ratios verification**
> double check ratio again [screenshots of full Ratios tab]

*Outcome:* All 30 ratio outputs verified mathematically. Checks included: EVA uses start-of-year capitalization (77,368) giving −1,835 ✓; Du Pont ROA = asset turnover × operating profit margin = 4.3% matches direct ROA ✓; Du Pont ROE (6.8%) intentionally differs from direct ROE (6.9%) due to time mismatch documented in Notes tab ✓. Zero errors found.

---

**Prompt 21 — Final submission check**
> double check the file and make sure i can submit it now

*Outcome:* Final comprehensive scan of all 6 tabs confirmed: Cover intact, BS ties both years, IS correct, CF correct, Ratios 30/30 correct, Notes fully populated with sources. File cleared for submission.

---

### LLM contribution vs. author contribution (Stage 3)

| LLM did | Author verified / decided |
|---|---|
| Populated all three financial statements from AR2025 PDF | Confirmed each number against source before approving |
| Identified unit error (shares in absolute vs. millions) | Caught the issue via peer comparison |
| Diagnosed zero D&A causing wrong operating CF | Approved fix and confirmed COGS split logic |
| Corrected PP&E to gross + accumulated depr from Note 11 | Verified against AR2025 Note 11 |
| Identified 8 Notes tab gaps vs. peer standard | Decided which fields to add/change |
| Cross-verified all CF lines against AR2025 p.103 | Reviewed each correction before applying |
| Verified all 22 BS lines and all 13 IS lines vs. AR2025 | Confirmed no corrections needed |
| Verified all 30 ratio calculations mathematically | Reviewed verification output |
| Checked syllabus AI Use Policy compliance | Decided to update Prompt Log before submission |

---

*Additional entries will be added for Stages 4–5.*
