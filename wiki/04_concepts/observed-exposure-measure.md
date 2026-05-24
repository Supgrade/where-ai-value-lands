---
title: Observed Exposure (Massenkoff–McCrory Measure)
status: concept
tags:
  - concept
  - labor
  - measurement
  - empirical
last-updated: 2026-05-23
---

# Observed Exposure

> [!abstract] One-line
> An occupation-level AI displacement-risk measure that weights **what LLMs can theoretically do** by **how they are actually being used in work**, weighting automated > augmentative uses. Introduced by [[massenkoff-mccrory-labor-market-impacts-2026]].

## Construction

Three inputs combine at task level via O*NET (~800 US occupations × ~20k tasks):

1. **Eloundou β** ([[eloundou-beta-exposure]]) — theoretical LLM capability score per task: 1 (LLM alone halves task time), 0.5 (LLM + tools), 0 (neither).
2. **Anthropic Economic Index usage** — share of observed work-related Claude conversations matched to each O*NET task; whether usage is automated (full weight) or augmentative (half weight).
3. **Occupation employment weights** — task-level scores averaged to occupation via O*NET time-fractions, then to category via BLS employment.

Output: an occupation-level scalar between 0 and 1 representing the share of an occupation's work-time AI is observed to cover.

## What makes it different

Prior task-exposure measures (Eloundou et al. 2023; Acemoglu et al. 2022; Felten–Raj–Seamans 2021) project displacement risk from **capability alone**. Observed Exposure adds a **realized-deployment** layer: a task is only counted if it has sufficient real Claude traffic in professional settings.

The empirical payoff: BLS 2024–2034 occupational growth is anti-correlated with this measure (slope −6.07, R² 0.027) but **not** with Eloundou's β alone. Realized usage adds predictive value the theoretical measure lacks. See [[ai-exposure-vs-bls-growth]].

## What it reveals

- **A large gap between feasible and deployed.** Computer & Math: 94% theoretical / 33% observed. See [[theoretical-vs-observed-capability-gap]].
- **Who the most exposed workers are.** Computer programmers (74.5%), customer service reps (70.1%), data entry keyers (67.1%). See [[most-exposed-occupations]].
- **30% of workers with zero exposure** — cooks, mechanics, lifeguards, bartenders, dishwashers, dressing room attendants — the manual-physical floor.

## What it does not capture

- **Forward-looking shifts.** The measure is anchored in current Claude product surfaces (mid-2025 usage data). If frontier capabilities reach previously inaccessible task categories, the measure lags reality.
- **Cross-vendor diffusion.** Claude usage ≠ all LLM usage. ChatGPT, Copilot, Gemini, open-weight deployments are not captured.
- **Augmentation surplus.** Augmentative use is half-weighted; this is a methodological choice with consequences — augmentation that meaningfully raises productivity (without reducing worker count) is counted as half a displacement signal.
- **General-equilibrium effects.** Demand reallocation, new task creation, wage adjustment are downstream of the measure, not in it.
- **Conflict of interest.** The vendor measuring its own labor-market impact is itself the deployment surface. The published [HuggingFace dataset](https://huggingface.co/datasets/Anthropic/EconomicIndex) is reproducible but does not resolve the structural conflict.

## Relation to other exposure frameworks

- **Eloundou β (2023):** theoretical only. This measure uses β as input but adds usage.
- **Acemoglu et al. (2022):** uses online vacancy data. Industry-level rather than occupation-level. Different mechanism (firm posting).
- **Hampole et al. (2025):** university-hiring-network IV approach. Firm-level adoption causally identified. Different unit of analysis.
- **Brynjolfsson et al. (2025):** ADP payroll panel. Age-group focused. Compatible with this measure on the young-worker finding (see [[ai-young-worker-hiring-slowdown]]).
- **Tomlinson et al. (2025) "applicability":** measures the *type* of task–LLM fit. Adjacent rather than competing.

## Why it matters to *Where Value Lands*

- Provides the first labor-side measure that **closes the loop** between capability and deployment. Capability without diffusion is invisible to the labor market; diffusion without capability is impossible. Observed Exposure is the intersection.
- Operationalises [[diffusion-vs-innovation]] at occupation granularity.
- Anchors the labor side of the [[H2_u-curve-of-value]] story: exposure clusters at high-skill knowledge work, not low-skill service work.
- Establishes a **detectability threshold** (~1pp differential unemployment) for any future displacement claim.

## Related

- [[massenkoff-mccrory-labor-market-impacts-2026]] — source.
- [[theoretical-vs-observed-capability-gap]] — the headline finding the measure exposes.
- [[exposed-worker-demographics]] — who scores high on this measure.
- [[ai-young-worker-hiring-slowdown]] — first empirical signal from applying the measure.
- [[most-exposed-occupations]] — top-10 list under this measure.
- [[ai-exposure-vs-bls-growth]] — predictive validation against independent BLS forecasts.
- [[diffusion-vs-innovation]] — the broader frame this measure operationalises.
- [[task-based-framework]] — Acemoglu's macro frame this measure sits inside.
- [[capital-labor-divergence]] — labor-incidence story this measure feeds.
- [[scaling-gap]] — capability-vs-deployment gap at the enterprise layer; parallel phenomenon.
- [[autonomy-slider]] — the automated-vs-augmentative weighting echoes the autonomy spectrum.
- [[fusion-skills]] — the augmentative side of the weighting; what gets discounted at half weight.
- [[displacement]] — the concept this measure is the empirical instrument for.
