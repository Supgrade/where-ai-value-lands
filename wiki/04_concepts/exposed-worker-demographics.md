---
title: Demographics of AI-Exposed Workers
status: concept
tags:
  - concept
  - labor
  - demographics
  - empirical
last-updated: 2026-05-23
---

# Demographics of AI-Exposed Workers

> [!abstract] One-line
> Workers in occupations most exposed to AI (per [[observed-exposure-measure]]) are **older, more female, more white/Asian, much more educated, higher-paid, and less unionised** than workers in unexposed occupations. They are not the demographic the prior bear-case projection (Acemoglu) predicted.

## The pattern (per [[massenkoff-mccrory-labor-market-impacts-2026]] Figure 5)

Top quartile of exposure vs zero-exposure workers, Aug–Oct 2022 CPS (just before ChatGPT release):

| Dimension | Zero exposure | Top quartile | Difference |
|---|---|---|---|
| AI coverage % | 0.0% | 38.8% | +38.8 pp |
| **Demographics** | | | |
| Age | 41.0 | 42.9 | +1.9 |
| Female % | 38.8% | 54.4% | **+15.5 pp** |
| Hispanic % | 24.8% | 13.8% | −11.0 pp |
| White, non-Hispanic % | 54.5% | 65.1% | +10.6 pp |
| Black, non-Hispanic % | 13.2% | 9.7% | −3.5 pp |
| Asian, non-Hispanic % | 4.7% | 9.1% | +4.4 pp (≈2×) |
| Married % | 44.6% | 54.9% | +10.4 pp |
| **Education** | | | |
| Less than HS | 13.2% | 2.3% | −10.9 pp |
| HS diploma | 38.9% | 17.7% | −21.2 pp |
| Some college / assoc. | 30.0% | 25.5% | −4.6 pp |
| Bachelor's | 13.3% | 37.1% | **+23.8 pp** |
| Graduate degree | 4.5% | 17.4% | **+12.8 pp** (≈4×) |
| **Labor market** | | | |
| Hours/week | 37.5 | 38.7 | +1.2 |
| Hourly wage ($) | $22.23 | $32.69 | **+$10.45** (+47%) |
| Union member % | 11.7% | 5.3% | −6.4 pp |

See [[high-vs-low-exposure-worker-characteristics]] for the data citation.

## The headline asymmetries

- **Education is the strongest separator.** Workers with graduate degrees are **~4× over-represented** in the most-exposed quartile (17.4% vs 4.5%). Workers without a high-school diploma are **~6× under-represented** (2.3% vs 13.2%).
- **A 47% wage premium** distinguishes exposed from unexposed work. The exposed group earns $32.69 vs $22.23 per hour.
- **The female over-representation** (+15.5 pp) is large but lives alongside the education over-representation; the typical exposed worker is a college-educated woman in administrative, healthcare-records, marketing, or finance support work.
- **Union membership halves** in the exposed group (5.3% vs 11.7%), consistent with white-collar non-unionised work.

## Why this matters

### A direct contradiction (partial) with [[acemoglu-simple-macroeconomics]]

Acemoglu (2024) predicted the wage incidence of AI displacement would fall on **low-education, native-born women in administrative and routine cognitive work**. The Anthropic data shows the most-exposed workers are **highly educated** (37% Bachelor's; 17% graduate degree) and **higher-paid**, not low-education. The female over-representation aligns with the prediction; the education and wage profile contradicts it.

The two are not strictly incompatible — Acemoglu's measure was task-based from Eloundou's earlier work and lacked usage weighting; Anthropic's measure adds realized Claude deployment. The reconciliation may be that **task-level theoretical exposure** (Acemoglu) concentrates on routine clerical tasks performed by lower-education workers, but **realized LLM usage** (Anthropic) is happening disproportionately in higher-skill knowledge work because that's where current LLM products are sold, used, and trusted. As the [[theoretical-vs-observed-capability-gap]] closes, the incidence could shift downward — or the gap could remain structurally uneven.

This is **a live research disagreement, not a closed question**. Either prediction could be retrospectively correct; current evidence sides with Anthropic's empirical measure over Acemoglu's theoretical projection.

### A direct corroboration of the [[H2_u-curve-of-value]] labor-side story (sort of)

The labor-exposure profile produces a U-shape on a different axis from the value-stack U:

- **Top of the exposure U:** high-wage knowledge workers (programmers, analysts, lawyers, accountants).
- **Bottom of the exposure U:** manual-physical labor (cooks, mechanics, lifeguards) — protected by embodiment.
- **Middle:** semi-skilled service work, partially exposed.

If labor displacement eventually materialises (currently invisible per [[unemployment-did-exposed-workers]]), the burden lands on the upper half of the wage distribution — a notable inversion of prior automation waves (manufacturing automation hit the middle; offshoring hit the middle; AI hits the top).

### Surplus distribution implication for [[capital-labor-divergence]]

If exposed labor is the **already-higher-paid half** of the workforce, AI-driven productivity gains in those occupations route to **capital owners of the L4–L6 application layer** (Cursor, Anthropic, etc.) rather than to the displaced workers themselves. The lower half is untouched **in either direction** — neither displaced nor lifted.

The "AI hurts everyone equally" framing is wrong on the labor side. So is "AI displaces the most vulnerable first." Current evidence: AI exposure correlates positively with skill, education, and pay.

## Caveats

- **Snapshot pre-treatment.** The table is Aug–Oct 2022 — before ChatGPT release. Post-2022 demographic shifts within these groups are not captured here.
- **CPS occupation-level only.** No within-occupation skill-level decomposition. Within "Computer programmers" there are juniors and seniors; the table cannot show whether one is more exposed than the other.
- **US data.** Cross-bloc comparison is absent; the demographics of exposed workers in EU or East Asian labor markets is unknown.

## Related

- [[massenkoff-mccrory-labor-market-impacts-2026]] — source.
- [[high-vs-low-exposure-worker-characteristics]] — data citation.
- [[observed-exposure-measure]] — the measure these demographics are scored against.
- [[most-exposed-occupations]] — the occupational composition of the top-quartile group.
- [[acemoglu-simple-macroeconomics]] — the prior prediction this evidence partially contradicts.
- [[capital-labor-divergence]] — the surplus-distribution lens; this evidence updates the labor-incidence prediction.
- [[H2_u-curve-of-value]] — labor-side U-shape on a different axis from the value-stack U.
- [[ai-young-worker-hiring-slowdown]] — the entry-level signal that may indicate where the displacement actually lands.
- [[task-based-framework]] — Acemoglu's macro frame; this evidence sits inside it.
- [[diffusion-vs-innovation]] — why the realized-incidence differs from theoretical projection.
- [[fusion-skills]] — the labor-side capability question for the cohort most exposed.
- [[displacement]] — the concept this demographic profile is the empirical anchor for.
