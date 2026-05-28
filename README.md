# BUS 629 — Corporate Finance Project · AB SKF

**Author:** Hai Dang · VEMBA, Shidler College of Business, University of Hawai'i at Mānoa
**Subject company:** AB SKF (publ.) · SKFB.ST · Nasdaq Stockholm · GICS 20305010
**Course:** BUS-629 · International Corporate Finance · Prof. Adam Stauffer
**Reporting period:** FY2025 (Jan 1 – Dec 31, 2025), prior FY2024 · IFRS (EU), audited by PwC
**Currency:** MSEK unless noted · Cost of capital: 9.0% (class default)

---

## What you'll find here

This repository is the full audit trail of a five-stage corporate-finance project on AB SKF — the world's largest bearing manufacturer — covering company selection, a 30-ratio analytical framework, an LLM-executed analysis, and the spec retrospective that closes the methodology loop. All numerical claims trace to a single Excel model (`models/builds/`), all analytical claims trace to a single technical spec (`docs/specs/`), and every AI-assisted prompt is logged in [`deliverables/prompt-log.md`](deliverables/prompt-log.md). The project is structured for a sceptical reviewer: open the relevant directory README first, then the deliverable. Where Stage 2–5 outputs reference numerical figures, those figures are cross-checked against [`analysis/validation/`](analysis/validation/). Where Stage 5 LLM output deviates from manual computation, the discrepancy is flagged and explained in the verification table rather than silently corrected.

---

## Project Status — Five Stages

| # | Stage | Deliverable | Location | Commit |
|---|-------|-------------|----------|--------|
| 1 | Self-introduction | [`BIO.md`](BIO.md), [`RESUME.md`](RESUME.md) | repo root | initial |
| 2 | Company selection memo | [`2026-05-18-dang-skf-selection.md`](docs/decisions/2026-05-18-dang-skf-selection.md) | `docs/decisions/` | `624bbc2` (original) → `5ea9292` (post-feedback revision) |
| 2-fb | Feedback response | [`2026-05-27-dang-stage2-feedback-response.md`](docs/decisions/2026-05-27-dang-stage2-feedback-response.md) | `docs/decisions/` | Stage 5 commit |
| 3 | Excel financial model | [`2026-05-19-dang-skf-financials.xlsx`](models/builds/2026-05-19-dang-skf-financials.xlsx) | `models/builds/` | `5b4ccb5` |
| 4 | Technical spec + HIL iteration | [`2026-05-24-dang-skf-spec.md`](docs/specs/2026-05-24-dang-skf-spec.md) · [`2026-05-24-dang-skf-stage4-iteration.md`](analysis/validation/2026-05-24-dang-skf-stage4-iteration.md) | `docs/specs/`, `analysis/validation/` | `157a13f` |
| 5 | LLM analysis + verification + retrospective | [`2026-05-27-dang-skf-llm-raw.md`](deliverables/2026-05-27-dang-skf-llm-raw.md) · [`2026-05-27-dang-skf-stage5-verification.md`](analysis/validation/2026-05-27-dang-skf-stage5-verification.md) · [`2026-05-27-dang-skf-final-analysis.md`](deliverables/2026-05-27-dang-skf-final-analysis.md) · [`2026-05-27-dang-skf-spec-retrospective.md`](deliverables/2026-05-27-dang-skf-spec-retrospective.md) | `deliverables/`, `analysis/validation/` | Stage 5 commit |
| 5-xc | Extra credit — peer benchmarking | [`2026-05-27-dang-skf-peer-benchmark.md`](deliverables/2026-05-27-dang-skf-peer-benchmark.md) | `deliverables/` | Stage 5 commit |

Cross-stage artefact: [`deliverables/prompt-log.md`](deliverables/prompt-log.md) — every AI-assisted prompt and decision logged in order.

---

## Headline Finding (Stage 5)

**EVA FY2025 = MSEK (1,835)** — SKF generated negative economic profit because after-tax operating income (MSEK 5,128) sat below the capital charge (MSEK 6,963 at 9.0% × MSEK 77,368 start-of-year capitalisation). Du Pont decomposition isolates operating margin (5.60% on the spec's ATOI/Sales convention) as the binding ROE driver; a recovery to the peer benchmark of ~10% lifts Du Pont ROE by +539 bps to 12.2%. The reported-vs-adjusted bridge is the central investor-communication question: on SKF's published adjusted basis, operating margin reads 12.7% (below the 14% long-term target) and adjusted ROCE reads 14.3% (FY2024: 14.2%) — H1 confirmation and H3 partial confirmation hold on the adjusted basis even where the reported figures show worse cyclical optics. The planned 2026 Automotive separation (per AR 2025) is the strategic catalyst expected to lift the Industrial-only run-rate toward Timken-comparable territory. Peer benchmarking against SKF's own AR-identified competitor set (Schaeffler, NSK, NTN, JTEKT, Timken) places SKF as 2nd-of-6 on adjusted profitability and 1st-of-6 on capital structure conservatism — the European/Japanese cohort is materially weaker; Timken defines the achievable margin ceiling.

See [`deliverables/2026-05-27-dang-skf-final-analysis.md`](deliverables/2026-05-27-dang-skf-final-analysis.md) for the full analysis and [`deliverables/2026-05-27-dang-skf-peer-benchmark.md`](deliverables/2026-05-27-dang-skf-peer-benchmark.md) for the extra-credit peer comparison. All key SKF figures verified against AR 2025 (audit trail in [`deliverables/prompt-log.md`](deliverables/prompt-log.md)).

---

## Repository Layout

```
Corporate-Finance/
├── README.md                          # this file
├── BIO.md                             # Stage 1 — author bio
├── RESUME.md                          # Stage 1 — author resume
├── LICENSE                            # MIT 2026
├── .gitignore                         # excludes Excel temp, OS junk, secrets
├── Corporate Finance Master Spreadsheets.xlsx  # course-provided master template
├── docs/
│   ├── README.md
│   ├── decisions/                     # Stage 2 memo + Stage 5 feedback response
│   ├── specs/                         # Stage 4 technical spec
│   ├── plans/                         # working plans (intentionally lean)
│   └── templates/                     # reusable doc templates
├── models/
│   ├── README.md
│   ├── builds/                        # Stage 3 working Excel model
│   └── templates/                     # starter Excel templates
├── analysis/
│   ├── README.md
│   └── validation/                    # Stage 4 HIL iteration + Stage 5 verification
├── data/
│   ├── README.md
│   └── skf-financial-summary-2021-2025.md  # 5-year source data
└── deliverables/
    ├── README.md
    ├── prompt-log.md                            # cross-stage AI prompt log
    ├── 2026-05-27-dang-skf-llm-raw.md           # Stage 5 raw LLM output
    ├── 2026-05-27-dang-skf-final-analysis.md    # Stage 5 final
    ├── 2026-05-27-dang-skf-spec-retrospective.md  # Stage 5 retrospective
    └── 2026-05-27-dang-skf-peer-benchmark.md    # Stage 5 extra credit — peer benchmarking
```

All Stage 2–5 deliverables follow the naming convention `YYYY-MM-DD-dang-{company-slug}-{kind}.{ext}`. The single exception is `deliverables/prompt-log.md`, which is intentionally cross-stage.

---

## How to Navigate

| If you want to read… | Start here |
|----------------------|-----------|
| The final FY2025 analysis | [`deliverables/2026-05-27-dang-skf-final-analysis.md`](deliverables/2026-05-27-dang-skf-final-analysis.md) |
| The peer benchmark (extra credit) | [`deliverables/2026-05-27-dang-skf-peer-benchmark.md`](deliverables/2026-05-27-dang-skf-peer-benchmark.md) |
| The technical spec that drove it | [`docs/specs/2026-05-24-dang-skf-spec.md`](docs/specs/2026-05-24-dang-skf-spec.md) |
| The Excel model behind the numbers | [`models/builds/2026-05-19-dang-skf-financials.xlsx`](models/builds/2026-05-19-dang-skf-financials.xlsx) |
| The full AI-prompt audit trail | [`deliverables/prompt-log.md`](deliverables/prompt-log.md) |
| What I would change about the spec | [`deliverables/2026-05-27-dang-skf-spec-retrospective.md`](deliverables/2026-05-27-dang-skf-spec-retrospective.md) |
| How LLM numbers were cross-checked by hand | [`analysis/validation/2026-05-27-dang-skf-stage5-verification.md`](analysis/validation/2026-05-27-dang-skf-stage5-verification.md) |

---

## About the Author

Hai Dang is Head of People Experience at SKF Vietnam and a VEMBA candidate at the Shidler College of Business, University of Hawai'i at Mānoa. The Stage 2 selection rationale leverages this operational context; the analytical work is held to the same discipline as if conducted on an outside name. Full bio in [`BIO.md`](BIO.md); full resume in [`RESUME.md`](RESUME.md).

---

## License

[MIT](LICENSE) — © 2026 Hai Dang. Course-provided master spreadsheets remain the property of the course.
