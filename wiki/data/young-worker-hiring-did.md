---
title: Young-Worker (22–25) New-Job Starts DiD — Exposed vs Unexposed
status: data
tags:
  - data
  - labor
  - empirical
  - anthropic
  - did
  - canary-signal
last-updated: 2026-05-23
---

# Young-Worker New-Job Starts DiD

## Headline result

Per [[massenkoff-mccrory-labor-market-impacts-2026]] Figure 7, CPS panel 2016–2025, workers aged 22–25:

> **Pooled post-ChatGPT DiD coefficient: −14.3% of baseline hiring rate (SE 7.2).** Barely statistically significant (t ≈ 2.0).

The job-finding rate for young workers entering top-quartile-exposed occupations has fallen ~14% relative to the rate for young workers entering zero-exposure occupations, post-ChatGPT.

## Methodology

- **Outcome:** monthly job start rate among 22–25-year-olds (defined as reporting a job they did not have the previous month).
- **Treatment group:** entry into top-quartile-exposed occupations.
- **Control group:** entry into zero-exposure occupations.
- **Identification:** difference-in-differences around ChatGPT release (Nov 2022).
- **CPS panel dimension** used to track month-to-month transitions.

## Trend shape (Figure 7 top panel)

- 2016–2019: job-start rate for exposed occupations ~1.2–1.5% / month; unexposed ~2.0–2.5% / month. Exposed lower at baseline.
- 2020–2021: COVID-era volatility, large swings in both series.
- 2022: pre-treatment normalisation; exposed series ~1.3%, unexposed ~2.5%.
- **2024: visible divergence.** Exposed series decays toward ~0.8–1.0%; unexposed series remains stable at ~2.0%.
- Mid-2025: convergence in the most recent data points (within noise band).

## Corroboration

Brynjolfsson, Chandar & Chen (2025) — using ADP payroll data, different methodology — find a **6–16% employment drop for 22–25-year-olds in exposed occupations**. The wide range reflects multiple counterfactual specifications:
- The 6 pp drop is vs a flat-employment counterfactual.
- The 16 pp drop is from a within-firm design comparing similar workers in the same firm with different occupations.
- The decrease is attributed to slowed hiring, not increased separations.

Two independent methodologies — Anthropic's CPS-DiD and Brynjolfsson's ADP-within-firm — find the same effect direction and rough magnitude.

## What the framework cannot rule out

The source explicitly lists alternative explanations:

- **Workers stay at current jobs** rather than transition to new exposed roles.
- **Workers take different (non-exposed) jobs.**
- **Workers return to school** to retrain.
- **Mismeasurement.** Survey-based job-transition data is more vulnerable to error than separations (Fujita, Moscarini & Postel-Vinay 2024).
- **Sector-specific hiring slowdowns** (tech in particular has slowed post-2022 for non-AI reasons: interest rates, over-hiring correction).

## Why this matters to *Where Value Lands*

- **First detectable AI labor signal in the wiki.** Everywhere else in this source — unemployment, wages, employment levels — the signal is null. This is the one.
- **Validates the "canary in the coal mine" framing.** AI displacement may show up as **lost entry slots** before it appears as unemployment.
- **Reframes the detection problem.** Labor-market dashboards focused on unemployment will systematically miss AI displacement. Hiring-rate panels for under-25s are the leading indicator.
- **Implication for [[capital-labor-divergence]]:** the displacement falls on the entry-level cohort first. Capital owners and incumbent senior workers benefit; new graduates bear the cost.

## Related

- [[massenkoff-mccrory-labor-market-impacts-2026]] — source.
- [[ai-young-worker-hiring-slowdown]] — concept page that interprets this datum.
- [[observed-exposure-measure]] — exposure definition.
- [[unemployment-did-exposed-workers]] — the null sibling DiD.
- [[capital-labor-divergence]] — labor-incidence story.
- [[H2_u-curve-of-value]] — surplus-distribution implication.
- [[exposed-worker-demographics]] — the cohort whose entry slot is being eroded.
- [[task-based-framework]] — macro envelope.
- [[diffusion-vs-innovation]] — diffusion happening at firm level as labor reallocation.
