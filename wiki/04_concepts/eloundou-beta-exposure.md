---
title: Eloundou β — Theoretical LLM Task Exposure
status: concept
tags:
  - concept
  - measurement
  - labor
  - task-exposure
last-updated: 2026-05-23
---

# Eloundou β — Theoretical LLM Task Exposure

> [!abstract] One-line
> A task-level scoring of LLM theoretical capability used as input to most modern AI-exposure measures. β = 1 if an LLM alone can halve task time, 0.5 if LLM + tools can, 0 otherwise.

## Origin

Eloundou, T., Manning, S., Mishkin, P. & Rock, D. (2023). *GPTs are GPTs: An Early Look at the Labor Market Impact Potential of Large Language Models*. arXiv:2303.10130.

Constructed via a combination of human and GPT-4 annotation of all ~20,000 O*NET tasks. The framework distinguishes:

- **Directly exposed (β=1).** Task time can be reduced ≥50% by an LLM alone, with a 2,000-word input limit and no access to real-time facts.
- **Exposed with tools (β=0.5).** Task time can be reduced ≥50% with an LLM augmented by software for retrieval, image processing, etc.
- **Not exposed (β=0).** Time cannot be reduced ≥50% by LLM-based tooling.

## Why this measure dominates the literature

- **Granularity.** Operates at task level (O*NET tasks), not occupation level, enabling weighted aggregation by employment.
- **Capability-anchored.** Independent of any particular firm's deployment choices.
- **Reproducible.** Public ratings, established codebook.
- **Pre-deployment.** Compiled before mass LLM diffusion, so usable as a counterfactual measure.

## What it gets wrong (or under-specifies)

- **Theoretical, not realized.** β=1 does not imply usage. Many β=1 tasks see no actual LLM use ([[theoretical-vs-observed-capability-gap]]).
- **No automated/augmentative distinction.** A task could be β=1 because an LLM speeds it up alone, but in practice usage is augmentative — the worker still does the work. The measure does not weight these differently.
- **Static.** Captures capability as of early 2023. Frontier model jumps since then are not reflected.
- **No work-vs-leisure split.** A task that is β=1 may see all its LLM use in non-work settings; the measure does not exclude this.

These limitations motivate [[observed-exposure-measure]], which uses β as input but adds realized work-context usage as a second layer.

## Distribution of Claude usage by β (per [[massenkoff-mccrory-labor-market-impacts-2026]] Figure 1)

| Eloundou β | Share of observed Claude work-context usage |
|---|---|
| β = 1 | 68% |
| β = 0.5 | 29% |
| β = 0 | 3% |

**97% of observed Claude work-context usage falls on tasks Eloundou et al. classified as theoretically feasible.** This is the strongest empirical validation of the β framework to date — what theory said LLMs could do, real users actually do.

## Empirical predictive power

Standalone — limited. The Eloundou β alone is **not** correlated with BLS 2024–2034 projected occupational growth. It becomes predictive only when weighted by realized usage (see [[observed-exposure-measure]] and [[ai-exposure-vs-bls-growth]]).

This is the headline methodological finding of the Massenkoff–McCrory paper: theoretical capability without deployment is invisible in labor-market forecasts. Usage data is the missing layer.

## Related

- [[observed-exposure-measure]] — the realized-usage-weighted measure that builds on β.
- [[theoretical-vs-observed-capability-gap]] — the gap between β and observed deployment.
- [[massenkoff-mccrory-labor-market-impacts-2026]] — primary application of β in this wiki.
- [[acemoglu-simple-macroeconomics]] — earlier macro analysis using a related task-exposure approach.
- [[task-based-framework]] — Acemoglu's macro frame that consumes task-exposure measures.
- [[ai-task-exposure-decomposition]] — Acemoglu's task-incidence decomposition.
- [[ai-exposure-vs-bls-growth]] — empirical test of β-only vs usage-weighted exposure.
- [[diffusion-vs-innovation]] — the macro frame for why theoretical-only measures under-perform empirically.
