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

*Additional entries will be added for Stages 3–5.*
