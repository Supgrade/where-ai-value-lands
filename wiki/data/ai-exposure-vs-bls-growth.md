---
title: AI Exposure vs BLS 2024–2034 Employment Growth
status: data
tags:
  - data
  - labor
  - empirical
  - anthropic
  - bls
last-updated: 2026-05-23
---

# AI Exposure vs BLS 2024–2034 Employment Growth

## Headline statistic

Per [[massenkoff-mccrory-labor-market-impacts-2026]] Figure 4 and accompanying regression:

> A regression at the occupation level weighted by current employment finds **slope = −6.07 (SE 1.32), R² = 0.027**. For every 10-percentage-point increase in observed AI exposure, BLS projected 2024–2034 employment growth drops by **0.6 percentage points**.

The relationship is **weak in R² but statistically significant** and survives the BLS's own independently constructed projections.

**Critically: no equivalent correlation exists when using Eloundou et al. β (theoretical capability) alone.** Realized usage adds predictive value the theoretical measure lacks.

## What the scatter shows

Binned scatterplot with 25 equally sized bins; small squares mark named example occupations:

| Occupation | Approx. exposure | Approx. projected 2024–34 growth |
|---|---|---|
| Software developers | ~30% | **+14%** (top outlier) |
| Electricians | ~0% | +10% |
| Registered nurses | ~10% | +5% |
| Lawyers | ~18% | +3% |
| Accountants | ~30% | +4% |
| (avg trend) | 50% | ~0% |
| Customer service reps | ~70% | **−2.5%** |
| Cashiers | ~10% | **−6%** |

The trend line is **clearly downward sloping** through 25 binned points, despite the substantial residual variance (R² = 0.027 means 97% of variance is *not* explained by exposure).

## Interpretation

### What the result supports

- **Independent validation of [[observed-exposure-measure]].** BLS analysts (separate methodology, separate data, separate institution) produce growth forecasts that align directionally with Anthropic's usage-weighted exposure. Two independent measures pointing at the same occupations is meaningful triangulation.
- **Diffusion-aware exposure beats theoretical-only exposure.** The same data, scored with Eloundou's β alone, produces no significant correlation. Usage data is the missing layer. See [[theoretical-vs-observed-capability-gap]].
- **Software developers are the strategic outlier.** High exposure **and** high projected growth. The most plausible reading: developers are the workers who *use* AI most productively while their labor demand grows fastest (because the work AI enables — building more software — itself demands more developers, Jevons-Paradox-style). See [[jevons-paradox-ai]].

### What the result does not support

- **It is not a forecast of AI's labor impact.** BLS projections are themselves model-based and may already partially price in AI deployment. The correlation could reflect what BLS analysts *expect* rather than what will happen.
- **The R² is low.** 97% of cross-occupation growth variance is not explained by AI exposure. Other forces (demographic shifts, demand reallocation, business-cycle effects) dominate.
- **The "−0.6 pp per 10 pp" magnitude is modest.** Customer service reps at 70% exposure correspond to ~−4 pp adjustment; even a tripling of the slope leaves most occupations within their historical band.

## Why this matters to *Where Value Lands*

- **Bridges the empirical and projective frames.** The exposure measure is now anchored to an independent labor-economist forecast, not merely Anthropic-internal usage data.
- **Confirms the [[diffusion-vs-innovation]] frame at the BLS horizon.** Analysts are projecting that the diffusion *will* deepen and affect employment, even if current unemployment data shows no signal ([[unemployment-did-exposed-workers]]).
- **Updates [[H2_u-curve-of-value]].** Software developers as a high-exposure / high-growth outlier is a top-of-U story: developers occupy the L4–L6 application-layer interface and capture the surplus from automation rather than bearing the cost.

## Caveats

- **BLS projections have a mixed track record.** The source acknowledges that government growth forecasts have "added little predictive value beyond linear extrapolation of past trends." Massenkoff (2025) is cited.
- **Endogeneity.** BLS analysts read AI news; their projections may already incorporate the same exposure signal Massenkoff & McCrory measure. The independence of the two measures is partial, not clean.

## Related

- [[massenkoff-mccrory-labor-market-impacts-2026]] — source.
- [[observed-exposure-measure]] — the measure scored.
- [[eloundou-beta-exposure]] — the theoretical-only measure that does *not* correlate.
- [[most-exposed-occupations]] — the top-10 list driving the regression.
- [[theoretical-vs-observed-capability-gap]] — why theoretical alone fails.
- [[diffusion-vs-innovation]] — the frame that explains why usage-weighting matters.
- [[H2_u-curve-of-value]] — the strategic outlier story.
- [[jevons-paradox-ai]] — software developers as the demand-expansion case.
- [[capital-labor-divergence]] — surplus-distribution story.
