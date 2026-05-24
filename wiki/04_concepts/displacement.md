---
title: Displacement
status: working
tags:
  - concept
  - labor
  - empirical
  - bear-case
last-updated: 2026-05-23
---

# Displacement

The labor-side counterpart to [[capital-labor-divergence]]: the share of human work that AI **substitutes for** rather than **augments**, and where the cost of that substitution actually lands in the labor market. Displacement is distinct from augmentation along a single methodological axis — augmentation raises productivity of an existing worker, displacement reduces the marginal demand for that worker — but in practice the two run together, and the [[observed-exposure-measure]] is constructed precisely to weight them differently (full weight for automated use, half weight for augmentative use). The point of separating the concepts is to refuse the bull-frame elision under which "AI just helps people work better" describes everything happening at once.

## Theoretical vs observed: the measurement debate

The pre-2026 displacement literature ([[acemoglu-simple-macroeconomics]], Eloundou et al., Felten–Raj–Seamans) projected displacement risk from **theoretical task exposure** — what an LLM *could* do, scored from O*NET task descriptions. Acemoglu predicted incidence would fall on low-education clerical women. [[massenkoff-mccrory-labor-market-impacts-2026]] introduces the [[observed-exposure-measure]] which weights theoretical capability by realized Claude work-context usage, and finds the actual exposed cohort is **more educated, more white/Asian, older, and 47% higher-paid** than the population ([[exposed-worker-demographics]]). The gap between the two measures is itself the story: capability has run ~3× ahead of deployment in the most-exposed category ([[theoretical-vs-observed-capability-gap]]), and *which* projection eventually plays out depends on whether the diffusion lag closes evenly or stays structurally uneven. This is a live disagreement, not a closed question — the wiki's posture is to track both predictions in parallel.

## Why unemployment dashboards under-detect it

The headline empirical finding from the same 2026 source is that **conventional unemployment statistics do not detect AI displacement at the current scale**. The [[unemployment-did-exposed-workers]] DiD is flat post-ChatGPT (+0.002, SE 0.002, insignificant at the ~1pp differential detectability threshold). The only signal that survives is [[ai-young-worker-hiring-slowdown]]: a ~14% drop in 22–25-year-old job-start rates in exposed occupations, with senior incumbents unaffected. Brynjolfsson et al.'s ADP-payroll companion finding (6–16% employment drop in the same cohort) corroborates it. Two consequences fold back into the rest of the wiki: (1) displacement currently lands as *suppressed entry-level hiring inside knowledge work*, not as broad-based layoffs — the incidence is intra-class (incumbent vs entrant), not inter-class; (2) the surplus is captured by capital owners of L4–L6 application-layer firms ([[application-layer]]) plus the firms saving on junior salaries, with labor seeing neither side of the wedge. The [[task-based-framework]] macro envelope still bounds the magnitude (<0.71% 10-year US TFP), but the distributional story sits *inside* that envelope and is sharp regardless.

## Related

- [[capital-labor-divergence]] — the macro frame this concept operationalises on the labor side.
- [[observed-exposure-measure]] — the usage-weighted measure that reframes the incidence question.
- [[theoretical-vs-observed-capability-gap]] — the ~3× gap that makes the projection contested.
- [[exposed-worker-demographics]] — who the realized-exposure cohort actually is.
- [[ai-young-worker-hiring-slowdown]] — the only detectable signal; entry-level channel.
- [[unemployment-did-exposed-workers]] — the null finding that makes the displacement invisible.
- [[acemoglu-simple-macroeconomics]] — the prior theoretical projection partly contradicted by observed data.
- [[massenkoff-mccrory-labor-market-impacts-2026]] — Anthropic 2026 source.
- [[eloundou-beta-exposure]] — theoretical scoring used as input to observed measures.
- [[task-based-framework]] — macro envelope inside which the displacement story sits.
- [[fusion-skills]] — the augmentation pole this concept is defined against.
- [[autonomy-slider]] — the design surface that makes the displacement/augmentation distinction visible.
- [[diffusion-vs-innovation]] — diffusion is what scales displacement as deployment catches capability.
- [[application-layer]] — where the L4–L6 surplus-capturing products live.
- [[bear-case-synthesis]] — the broader frame this concept updates.
