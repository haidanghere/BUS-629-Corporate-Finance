---
template: memo
purpose: "Executive memo for stage 1 / 2 deliverables — problem framing, analysis summary, and recommendation"
audience: student
fields_required: [title, to, from, date, re, executive_summary, background, method, findings, implications, limitations, references]
naming_convention: "YYYY-MM-DD-{slug}.md"
courses: [BUS-629]
title: "Company Selection Memo — AB SKF"
to: "Professor Adam Stauffer"
from: "Hai Dang"
date: 2026-05-19
re: "Stage 2 Company Selection — AB SKF (SKFB: Nasdaq Stockholm)"
stage: 2
---

# Company Selection Memo — AB SKF

**To:** Professor Adam Stauffer
**From:** Hai Dang
**Date:** 2026-05-19
**Re:** Stage 2 Company Selection — AB SKF (SKFB: Nasdaq Stockholm)

---

## Executive Summary

This memo selects AB SKF (SKFB: Nasdaq Stockholm) as the subject company for the BUS 629 ratio analysis project. SKF is a Swedish industrial manufacturer of bearings, seals, and lubrication systems with FY2025 net sales of SEK 91,583M (~USD 8.6B). The selection is grounded in direct professional familiarity — I serve as Head of People Experience at SKF Vietnam — a five-year analytical arc defined by a major Automotive divestiture (2023) and a 2025 global restructuring program, and confirmed access to five years of audited IFRS financials. The central question: do SKF's one-time restructuring charges represent genuine structural transformation, or recurring earnings volatility?

---

## Background

AB SKF is the world's leading bearing manufacturer, operating across 40+ countries with FY2025 net sales of SEK 91,583M, market cap ~SEK 112B (B-share: SEK 245.8), and credit ratings of Baa1/BBB+ (Moody's/Fitch). Reporting currency: SEK; accounting standard: IFRS, audited by PwC.

I selected SKF because I work directly at SKF Vietnam as Head of People Experience, giving me operational context that sharpens ratio interpretation beyond what an external analyst can bring. The 2021–2025 window spans three structurally distinct phases: a two-segment structure (Industrial + Automotive) through 2022; the Automotive divestiture to Magna International (announced June 2022, closed 2023), which fundamentally refocused the portfolio; and a 2025 global rightsizing program (MSEK –3,918 in items affecting comparability) that depressed reported operating margin to 8.5% while adjusted margin held at 12.7%. The reported-vs-adjusted gap is the recurring analytical thread throughout this project.

---

## Method

Five Annual Reports (2021–2025) accessed directly from skf.com; key figures verified against audited financial statements and Alternative Performance Measures (APM) disclosures. Both reported and adjusted figures tracked in parallel across all five years (IAC: 2021 –81; 2022 –1,672; 2023 –1,893; 2024 –1,844; 2025 –3,918 MSEK). Peer comparison data sourced from Morningstar (Schaeffler, NSK, Timken); share and dividend data from Nasdaq Stockholm; historical FX rates from Riksbank. Analysis covers five ratio categories: profitability, efficiency, liquidity, leverage, and valuation. Industrial-only segment data used for 2021–2022 to ensure comparability with the post-divestiture 2023–2025 single-segment structure. Verified five-year data filed at `data/skf-financial-summary-2021-2025.md`.

---

## Findings

Initial data review surfaces three testable hypotheses:

1. **I expect the 2023 Automotive divestiture to explain the majority of post-2022 margin improvement** because Automotive dragged group margins throughout 2021–2022 (Automotive: 6.3% in 2021, 2.4% in 2022 vs. Industrial: 15.9% and 11.3%). Transition effects — contract manufacturing run-off and separation-related restructuring — may delay full visibility into 2025 results. I will test this by isolating Industrial performance and separating portfolio-mix effects from underlying margin improvement within the business.

2. **I expect net debt/EBITDA to show the most consistent deleveraging path of any leverage metric**, falling from 1.5x (2022) to 1.0x (2025) alongside net debt/equity declining from 38.3% to 21.6%. I will test whether this path is smoother than other leverage measures and decompose how much improvement comes from EBITDA growth versus actual debt reduction.

3. **I expect adjusted ROCE to remain closer to SKF's 14% long-term target than reported ROCE**, which I expect to show wider dispersion due to restructuring and separation-related charges (IAC: –1,893 in 2023; –1,844 in 2024; –3,918 in 2025). I will test this by comparing the dispersion of adjusted versus reported ROCE and reconciling the gap to identified one-time items. If this volatility persists beyond the current restructuring cycle, it would suggest these items are not truly non-recurring.

---

## Implications

If all three hypotheses hold, the analysis will demonstrate that SKF's post-divestiture Industrial business is structurally more profitable than consolidated historical results suggest, and that restructuring charges reflect genuine transformation cost rather than recurring earnings erosion. For valuation, this matters substantially: SKF's 2025 reported P/E of 28.5x normalizes to approximately 13x on adjusted earnings — a materially different picture for peer benchmarking against Schaeffler, NSK, and Timken, and a direct test of whether management's adjusted-figure narrative is credible.

---

## Limitations & Next Steps

Three constraints apply: (1) NSK peer data requires J-GAAP-to-IFRS adjustments for leverage and profitability ratios — differences will be flagged where material; (2) SKF's SEK-denominated reporting means FX translation effects can overstate or understate year-over-year trends (2025 net sales reduced by –6.6 percentage points by currency alone); (3) 2021–2022 two-segment data is not directly comparable to the post-2023 single-segment structure without an Industrial-only carve-out. Stage 3 model build will address all three.

---

## References

- AB SKF. (2022–2026). *Annual Reports 2021–2025*. Retrieved from skf.com/group/investors
- Morningstar. (2026). *AB SKF — Key Ratios and Peer Comparison*. Retrieved from morningstar.com
- Nasdaq Nordic. (2026). *SKFB Share Data*. Retrieved from nasdaqomxnordic.com
- Svenska Riksbanken. (2026). *Historical Exchange Rates SEK/USD 2019–2025*. Retrieved from riksbank.se
