---
title: Unemployment DiD — Exposed vs Unexposed Workers (2016–2025)
status: data
tags:
  - data
  - labor
  - empirical
  - anthropic
  - did
last-updated: 2026-05-23
---

# Unemployment DiD — Exposed vs Unexposed Workers

## Headline result

Per [[massenkoff-mccrory-labor-market-impacts-2026]] Figure 6, CPS 2016–2025:

> **Pooled post-ChatGPT (Nov 2022 – mid 2025) DiD coefficient: +0.0020 (SE 0.0019).**
>
> Statistically indistinguishable from zero. The unemployment gap between top-quartile-exposed and zero-exposure workers has *not* widened since the release of ChatGPT.

## Methodology

- **Treatment group:** workers in top quartile of observed exposure (per [[observed-exposure-measure]]).
- **Control group:** workers in zero-exposure occupations (~30% of US workers).
- **Identification:** difference-in-differences with ChatGPT release (Nov 2022) as treatment timing.
- **Robustness checks (per Appendix):**
  - Vary percentile cutoff from median to 95th. In all cases the post-treatment coefficient is flat or *negative* (unemployment *decreasing* in the exposed group relative to control).
  - Restrict to young (22–25) workers. Coefficient remains flat (the young-worker effect is in *hiring*, not unemployment — see [[ai-young-worker-hiring-slowdown]]).
  - Substitute Department of Labor UI claims for CPS survey-based unemployment. No clear impact on exposed jobs.

## Trend shape (Figure 6 top panel)

- 2016–2019: top-quartile unemployment rate **lower** than no-exposure (white-collar baseline advantage).
- 2020 COVID shock: no-exposure (in-person) workers see unemployment spike to ~18%; exposed workers spike to ~10%. The shock affects **less** exposed workers far more.
- 2021–2022: rapid convergence as COVID normalises.
- 2022 onwards: parallel trends. Top-quartile unemployment hovers ~3–4%; no-exposure ~5–6%.
- Post-2022: no visible divergence; ChatGPT release does not produce a structural break.

## Detectability frontier

The 95% confidence interval on the post-ChatGPT coefficient permits detection of **differential unemployment increases on the order of 1 percentage point**. A scenario in which all workers in the top 10% of exposure were laid off would lift top-quartile unemployment from 3% to 43% and aggregate from 4% to 13% — easily detectable. A "white-collar Great Recession" (top-quartile doubling from 3% to 6%) would also be visible.

What the framework *cannot* detect:

- Slow trickle below 1pp differential.
- Exit from the labor force (workers stop searching).
- Hiring suppression without separation (which is the channel the young-worker finding suggests is active — see [[ai-young-worker-hiring-slowdown]]).
- Wage suppression without unemployment.
- Reallocation within an occupation.

## Interpretation

### What the result supports

- **No detectable AI displacement in unemployment data as of mid-2025.** Two-and-a-half years post-ChatGPT, the labor-market dashboard most policy-makers watch shows no signal.
- **The "white-collar Great Recession" scenario has not happened.** A common worry — that AI would crush the educated middle class — is not supported by the current data.

### What the result does not support

- **It does not rule out AI labor effects.** Three channels are not measured: hiring (visible separately in [[ai-young-worker-hiring-slowdown]]), labor-force exit, and wage suppression.
- **It is short-horizon.** Two-and-a-half years is brief for a labor-market shift driven by capital reallocation and skill retraining.
- **It depends on the exposure measure.** If the [[observed-exposure-measure]] systematically misclassifies the *truly* exposed occupations (which the source's own validation against BLS partially addresses — see [[ai-exposure-vs-bls-growth]]), the DiD is testing the wrong cells.

## Why this matters to *Where Value Lands*

- **Adjudicates the "AI is already destroying jobs" claim.** It is not, at least not at the resolution unemployment data can detect.
- **Tightens the detectability question.** Any future paper claiming AI displacement must clear the ~1pp differential threshold.
- **Reframes the labor-incidence channel.** Since unemployment is flat, the labor-side displacement (if any) must show up elsewhere — hiring (active signal per [[ai-young-worker-hiring-slowdown]]), labor-force exit (not measured), or wage suppression (visible in [[high-vs-low-exposure-worker-characteristics]] cross-section but no time-series here).

## Related

- [[massenkoff-mccrory-labor-market-impacts-2026]] — source.
- [[observed-exposure-measure]] — exposure definition.
- [[ai-young-worker-hiring-slowdown]] — the *positive* signal that does survive.
- [[young-worker-hiring-did]] — the parallel DiD that does show an effect.
- [[capital-labor-divergence]] — surplus-distribution story consistent with flat unemployment + slowed entry-level hiring.
- [[task-based-framework]] — macro envelope.
- [[H2_u-curve-of-value]] — labor-side absence of harm = surplus stays with capital.
