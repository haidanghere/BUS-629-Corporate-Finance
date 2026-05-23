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

This memo selects AB SKF (SKFB: Nasdaq Stockholm) for the BUS 629 ratio analysis project. SKF is a Swedish industrial manufacturer (bearings, seals, lubrication systems) with FY2025 net sales of SEK 91,583M. The analytical window (2021–2025) spans an Automotive divestiture (2023) and a 2025 global restructuring program — creating a persistent reported-vs-adjusted gap that is the central question of this project.

---

## Background

AB SKF is the world's leading bearing manufacturer, reporting in SEK under IFRS (audited by PwC). I work at SKF Vietnam as Head of People Experience, giving me operational context that sharpens ratio interpretation. The 2021–2025 window covers three phases: a two-segment structure (Industrial + Automotive) through 2022; the Automotive divestiture to Magna International (closed 2023); and a 2025 rightsizing program (MSEK –3,918 in items affecting comparability) that depressed reported operating margin to 8.5% while adjusted margin held at 12.7%.

---

## Method

Five Annual Reports (2021–2025) from skf.com, verified against audited financials and APM disclosures. Reported and adjusted figures tracked in parallel. Peers: Schaeffler, NSK, Timken (Morningstar). Industrial-only segment data used for 2021–2022 to ensure comparability with the post-2023 single-segment structure. Five ratio categories covered: profitability, returns on capital, leverage, efficiency, and liquidity. Source data filed at `data/skf-financial-summary-2021-2025.md`.

---

## Findings

Three testable hypotheses:

1. **I expect the 2023 Automotive divestiture to explain the majority of post-2022 margin improvement** because Automotive dragged group margins throughout 2021–2022 (Automotive: 6.3% in 2021, 2.4% in 2022 vs. Industrial: 15.9% and 11.3%). I will test this by isolating Industrial-segment performance and separating portfolio-mix effects from underlying operational improvement.

2. **I expect net debt/EBITDA to show the most consistent deleveraging path of any leverage metric**, falling from 1.5x (2022) to 1.0x (2025). I will test whether this path is smoother than other leverage measures and decompose how much improvement comes from EBITDA growth versus actual debt reduction.

3. **I expect ROCE to recover toward SKF's 14% long-term target by 2025 because the Automotive divestiture removes low-return capital from the employed base** — Automotive ROCE was materially below Industrial ROCE throughout 2021–2022. I will test this by decomposing ROCE changes into margin improvement (EBIT/Sales) versus capital turn improvement (Sales/Capital Employed), distinguishing portfolio-mix effects from operational efficiency gains. If ROCE fails to recover despite the divestiture, it would suggest the remaining Industrial business carries structural capital inefficiency.

---

## Implications

If all three hypotheses hold, SKF's Industrial business is structurally more profitable and capital-efficient than consolidated historical results suggest. For valuation, SKF's 2025 reported P/E of 28.5x normalizes to approximately 13x on adjusted earnings — a materially different benchmark for peer comparison against Schaeffler, NSK, and Timken.

---

## Limitations & Next Steps

Three constraints: (1) NSK peer data requires J-GAAP-to-IFRS adjustments — differences flagged where material; (2) SEK reporting means FX translation can distort year-over-year trends (2025 net sales reduced –6.6 pp by currency); (3) 2021–2022 two-segment data requires Industrial-only carve-out for post-2023 comparability. Stage 3 model build addresses all three.

---

## References

- AB SKF. (2022–2026). *Annual Reports 2021–2025*. Retrieved from skf.com/group/investors
- Morningstar. (2026). *AB SKF — Key Ratios and Peer Comparison*. Retrieved from morningstar.com
- Nasdaq Nordic. (2026). *SKFB Share Data*. Retrieved from nasdaqomxnordic.com
- Svenska Riksbanken. (2026). *Historical Exchange Rates SEK/USD 2019–2025*. Retrieved from riksbank.se
