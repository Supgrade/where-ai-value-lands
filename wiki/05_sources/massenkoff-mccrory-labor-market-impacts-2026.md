---
title: Massenkoff & McCrory — Labor Market Impacts of AI (Anthropic, 2026)
status: draft
tags:
  - source
  - labor
  - empirical
  - anthropic
  - bull-frame-internal
last-updated: 2026-05-23
---

# Massenkoff & McCrory — Labor Market Impacts of AI: A New Measure and Early Evidence

## Citation

**Massenkoff, M. and McCrory, P.** (2026). *Labor market impacts of AI: A new measure and early evidence*. Anthropic, March 5, 2026. https://www.anthropic.com/research/labor-market-impacts

Anthropic in-house research note. Acknowledges feedback from Martha Gimbel, Anders Humlum, Evan Rose, Nathan Wilmers. Data available via [HuggingFace: Anthropic/EconomicIndex](https://huggingface.co/datasets/Anthropic/EconomicIndex).

## Central claim

A new occupation-level measure of AI displacement risk — **[[observed-exposure-measure]]** — combines theoretical LLM capability (Eloundou et al. 2023 β), real-world Claude usage from the [Anthropic Economic Index](https://www.anthropic.com/economic-index), and O*NET task taxonomy, weighting automated > augmentative uses and work-related > leisure uses. Applied to US Current Population Survey data from 2016–2025, it finds **no detectable AI effect on aggregate unemployment** through late 2025, but **suggestive evidence of slowed hiring for workers aged 22–25 in highly exposed occupations** post-ChatGPT (DiD pooled post ≈ −14% of baseline hiring rate, SE 7.2).

## Key findings

1. **AI is far from reaching its theoretical capability.** Observed Claude task coverage is a small fraction of what Eloundou et al. classify as theoretically feasible. In Computer & Math, theoretical coverage is ~94%, observed only ~33%. See [[theoretical-vs-observed-capability-gap]].
2. **Most exposed occupations are knowledge-work, not low-skill service work.** Computer programmers (74.5%), customer service reps (70.1%), data entry keyers (67.1%), medical record specialists (66.7%). See [[most-exposed-occupations]].
3. **BLS 2024–2034 employment projections are weakly but significantly anti-correlated with observed exposure.** Slope −6.07 (SE 1.32), R² 0.027: a 10pp coverage increase corresponds to a 0.6pp drop in projected growth. The relationship does **not** hold for the Eloundou et al. theoretical β alone — actual usage data adds predictive value. See [[ai-exposure-vs-bls-growth]].
4. **Exposed workers are older, female, more white/Asian, more educated, higher-paid, and less unionised.** Top-exposure-quartile vs zero-exposure: +15.5pp female, +23.8pp Bachelor's, +12.8pp graduate degree, $32.69 vs $22.23 hourly wage (47% higher). See [[exposed-worker-demographics]] and [[high-vs-low-exposure-worker-characteristics]].
5. **No detectable unemployment impact** for top-quartile-exposed workers vs unexposed group post-ChatGPT. DiD pooled post +0.0020 (SE 0.0019). Robust across percentile cutoffs, UI-claims data, and CPS subgroups. See [[unemployment-did-exposed-workers]].
6. **Young-worker hiring slowdown is the only detectable signal.** Job-finding rate for 22–25-year-olds entering exposed occupations dropped ~14% post-ChatGPT vs entry into unexposed occupations (barely statistically significant). Echoes Brynjolfsson, Chandar & Chen (2025) "canaries in the coal mine" finding. See [[ai-young-worker-hiring-slowdown]].
7. **Detectability threshold.** Current CI permits detection of differential unemployment increases on the order of ~1pp. A "white-collar Great Recession" scenario (top-quartile unemployment rising from 3% to 6%) would be visible; a slow grind beneath that threshold would not.

## Figures interpreted

- **Figure 1.** 68% of Claude usage falls on β=1 tasks (fully feasible for an LLM alone), 29% on β=0.5 (LLM + tools), only 3% on β=0. Validates the Eloundou et al. theoretical scoring as a usage-relevant signal.
- **Figure 2.** Radar plot, observed vs theoretical coverage by occupational category. Observed (red) is uniformly smaller than theoretical (blue) and concentrated in Computer & Math, Business & Finance, Office & Admin. Physical-labor categories (Construction, Agriculture, Production, Installation & Repair, Food & Serving) sit near zero in both.
- **Figure 3.** Top-10 most-exposed occupations table. See [[most-exposed-occupations]].
- **Figure 4.** Binned scatter, BLS 2024–2034 projected growth vs observed exposure. Software developers are the *outlier*: very high exposure and very high projected growth (top-of-U archetype). Cashiers and customer service reps anchor the negative side. See [[ai-exposure-vs-bls-growth]].
- **Figure 5.** High vs low exposure demographics. See [[high-vs-low-exposure-worker-characteristics]].
- **Figure 6.** Unemployment-rate DiD, top-quartile vs unexposed, 2016–2025. The COVID shock (2020) is the dominant feature; post-2022 series flatten and converge. See [[unemployment-did-exposed-workers]].
- **Figure 7.** Young-worker (22–25) job-start rate, high-exposure vs unexposed occupations. Visual divergence in 2024; DiD pooled post −14.3% (SE 7.2). See [[ai-young-worker-hiring-slowdown]].

## Hypothesis touches

- **[[H1_L0-L7-ladder]]** — partial / oblique. The most-exposed occupations cluster in roles that *consume* L4–L6 application/agent products (programmers using copilots, customer service reps using chat tools, analysts using research agents). Confirms that the application-and-agent layer is where AI is actually being applied to work, not just demonstrated as capable.
- **[[H2_u-curve-of-value]]** — important pressure from the labor side. The labor-exposure shape is itself U-like but on a different axis: high-exposure = high-skill, high-wage knowledge work; zero-exposure = manual physical labor (cooks, mechanics, bartenders). This is **not** the value-stack U; it is a labor-exposure U. The two interact: AI's labor-side displacement maps to the application-layer top of H2, suggesting capital owners of L4–L6 platforms (Cursor, Anthropic itself) capture surplus while exposed knowledge workers either retain their jobs (so far) or face slowed hiring at the entry-level point of entry. The surplus then lands with capital, not labor — consistent with [[capital-labor-divergence]] and contradicting any "AI lifts all wages" narrative.
- **[[diffusion-vs-innovation]]** — direct empirical anchor. The headline methodological finding — theoretical capability is **far** ahead of observed deployment — operationalises Ding's diffusion-marathon thesis at the firm/worker level. Capability has run ahead of diffusion by roughly 3× in the most-exposed category (94% theoretical / 33% observed in Computer & Math). The "red area will grow to cover the blue" is the diffusion process itself.

## Open questions surfaced

1. **What happens to the surplus when deployment catches up to capability?** If the red area grows to fill the blue over 5–10 years, and BLS already projects 0.6pp less growth per 10pp coverage, the magnitude of labor displacement compounds. But the paper does not estimate this trajectory.
2. **Is "slowed hiring" the right early indicator?** The young-worker finding is the only signal that survives. If AI labor effects show up first as suppressed entry-level hiring rather than rising unemployment, conventional labor-market dashboards may miss the disruption entirely (workers exit the labor force or return to school rather than appearing as unemployed).
3. **Acemoglu vs Anthropic on the incidence question.** Acemoglu (2024) predicted the wage incidence would fall on **low-education native-born women in administrative work**. This source finds exposed workers are **more educated, higher-paid, more white/Asian** than the population — a different cohort entirely. Either the prediction was wrong, the measure captures a different slice, or both. See [[exposed-worker-demographics]] for the unresolved contradiction.
4. **Why does the Eloundou β alone not predict BLS growth, but the usage-weighted measure does?** This is the strongest argument for usage-weighting in exposure measurement, but it raises a methodological worry: usage patterns are endogenous to current Claude product surfaces and may misrepresent future AI capability mix.
5. **Does the data-availability publication of the index ([HuggingFace](https://huggingface.co/datasets/Anthropic/EconomicIndex)) shift the methodological norm?** Anthropic is publishing its own usage-derived measure of labor impact while it deploys models that drive that impact. The conflict-of-interest dimension is unstated in the source but is itself an open question for any external reader.

## Methodological notes

- **Measure construction.** For each O*NET task: count as "covered" if (a) Eloundou β=1 (or β=0.5 with appropriate tools), (b) sufficient work-related Claude usage in the Economic Index, with (c) full weight for automated usage patterns and half weight for augmentative patterns. Aggregate to occupation via time-weighting per task.
- **Identification.** Difference-in-differences using ChatGPT release (Nov 2022) as treatment timing. Top-quartile-exposed workers (treated) vs zero-exposure workers (control). Spearman rank correlation across alternative specifications is "exceedingly high" per appendix.
- **Caveats acknowledged in source.** Many young workers without listed occupation in CPS may exit labor force rather than appear unemployed (so unemployment is the wrong metric for the canary-in-coal-mine effect). Two-year window may be too short. The measure depends on the current Claude product mix and is forward-projectable only to the extent the mix is.

## Why this matters to *Where Value Lands*

- It is the **first systematic, empirically grounded labor-side measure** that connects directly to the value-stack story.
- It validates the [[diffusion-vs-innovation]] frame with measurable scale: capability is 3× ahead of deployment in the most-exposed sector.
- It contradicts the bear-case "AI is hitting low-skill women in admin work" framing without dispatching it — the disagreement is a research front, not closed.
- It sets a **detectability frontier** (1pp differential unemployment, ~14% hiring-rate suppression for 22–25 cohort) that any future labor-side claim about AI must clear.
- It is internal Anthropic research: useful as a bull-frame internal datapoint, but should be **triangulated** against external sources (Brynjolfsson et al. 2025; Hampole et al. 2025; OECD; Gimbel/Budget Lab).

## See also

- [[observed-exposure-measure]] — the new measure itself.
- [[theoretical-vs-observed-capability-gap]] — the "red will grow to cover the blue" diffusion lag.
- [[exposed-worker-demographics]] — who the exposed workers actually are.
- [[ai-young-worker-hiring-slowdown]] — the only detectable signal.
- [[most-exposed-occupations]] — Figure 3 data.
- [[ai-exposure-vs-bls-growth]] — Figure 4 data.
- [[high-vs-low-exposure-worker-characteristics]] — Figure 5 data.
- [[unemployment-did-exposed-workers]] — Figure 6 data.
- [[young-worker-hiring-did]] — Figure 7 data.
- [[H2_u-curve-of-value]] — the labor-side mirror to the value-stack U.
- [[capital-labor-divergence]] — labor-side incidence question; partial contradiction with Acemoglu's prediction.
- [[diffusion-vs-innovation]] — measurement layer for Ding's thesis at the worker level.
- [[scaling-gap]] — sibling phenomenon: capability outruns deployment at both worker and enterprise levels.
- [[task-based-framework]] — the macro envelope that the labor-displacement story sits inside.
- [[acemoglu-simple-macroeconomics]] — prior prediction this source partially contradicts.
- [[bear-case-synthesis]] — the broader frame this evidence updates.
