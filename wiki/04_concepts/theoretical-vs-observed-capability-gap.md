---
title: Theoretical-vs-Observed AI Capability Gap
status: concept
tags:
  - concept
  - diffusion
  - empirical
  - measurement
last-updated: 2026-05-23
---

# Theoretical-vs-Observed Capability Gap

> [!abstract] One-line
> The share of work tasks LLMs **could theoretically perform** is several times larger than the share they are **actually observed performing in professional settings**. The gap is the diffusion process; how fast it closes determines when labor effects become visible.

## The empirical artefact

Per [[massenkoff-mccrory-labor-market-impacts-2026]] Figure 2:

| Occupational category | Theoretical (Eloundou β) | Observed (Claude usage) |
|---|---|---|
| Computer & Math | ~94% | ~33% |
| Office & Admin | ~90% | ~10–15% |
| Business & Finance | ~75% | ~15–20% |
| Legal | ~70% | ~5% |
| Education & library | ~80% | ~5% |
| Construction / Agriculture / Production / Installation | <10% | ~0% |

Even in the most-exposed category, **actual deployment is roughly one-third of capability**. In Legal and Education, capability is high but observed work-context use is near zero — usage exists but is mostly classified as personal/leisure or otherwise out of scope.

## What drives the gap

The source lists five concrete drivers:

1. **Model limitations.** Theoretically feasible tasks may still fail in practice (hallucination, context limits, weak tool use).
2. **Legal and compliance constraints.** Healthcare (drug-refill authorisations, prescription information) and legal (representing clients in court) are gated even where the cognitive task is in scope.
3. **Software / integration requirements.** Tasks require API surfaces, system access, identity verification that LLM products do not yet expose at scale.
4. **Human verification steps.** Many workflows require a human in the loop even when the model could in principle proceed — see [[autonomy-slider]].
5. **Workflow lock-in.** Existing tools and habits are sticky; substitution requires retraining, re-tooling, and trust.

These are exactly the [[oecd-sme-enabler-quartet]] (skills, finance, connectivity, AI-enabling inputs) at the firm level — and at the worker level, [[ai-skill-shortage-as-diffusion-bottleneck]] is the dominant binding constraint.

## What the gap closing looks like

The source's framing: *"As capabilities advance, adoption spreads, and deployment deepens, the red area will grow to cover the blue."*

Three interpretations of how:

- **Linear catch-up.** Deployment grows roughly proportionally with capability over 5–10 years; effects scale linearly with the share covered.
- **Saturated catch-up.** Deployment is governed by the binding constraint that varies by task (legal compliance vs API integration vs trust); some categories close fast, others never close. The eventual deployment shape is uneven across O*NET categories.
- **Frontier-shifting.** Capability itself moves; the blue area grows faster than the red can catch up. In this regime, the gap never closes — the measure of theoretical-vs-observed becomes a moving target.

The source assumes implicitly the second pattern (different binding constraints in different categories) and offers the methodology as a tool to track which categories are closing fastest.

## Why this matters to *Where Value Lands*

- **Operationalises diffusion at the work-task level.** [[diffusion-vs-innovation]] is largely macro; this is the same idea at occupation granularity. The Ding diffusion-marathon thesis is supported empirically: capability has run ahead of diffusion by ~3× in the most exposed category.
- **Frames the labor-market timing question.** Labor effects are not currently detectable in unemployment data (see [[unemployment-did-exposed-workers]]). The gap explains *why*: deployment is still narrow. If/when the red area expands to ~70–80% of the blue, the labor effects implied by [[exposed-worker-demographics]] become much harder to avoid.
- **Parallels [[scaling-gap]] at a different level.** The 74% enterprise scaling gap is the same phenomenon measured at firm level. Both gaps are the **diffusion process** — and both are interpretation-flexible: bull frames see them as closing through better enablers; bear frames see them as evidence that AI does not deliver durable value at scale.

## What would change the picture

- **Sustained, broad-based growth in observed coverage** without a parallel improvement in BLS growth projections. That would be evidence the diffusion is happening but the macroeconomic incidence is mild (compatible with [[task-based-framework]]'s <0.71% TFP cap).
- **A widening gap.** Capability advances (frontier-model jumps; agentic capabilities; world models per [[world-models-jepa]]) outpace deployment, meaning the measure of theoretical capability is itself unstable.
- **An aggressive closing of the gap in specific categories** (Computer & Math first; Legal or Healthcare second wave) accompanied by visible labor effects. This is the scenario the source's framework is best positioned to detect.

## Related

- [[massenkoff-mccrory-labor-market-impacts-2026]] — source.
- [[observed-exposure-measure]] — the measurement instrument that quantifies the gap.
- [[eloundou-beta-exposure]] — the theoretical-capability score used as input.
- [[diffusion-vs-innovation]] — the broader frame this gap operationalises.
- [[scaling-gap]] — the enterprise-level twin.
- [[oecd-sme-enabler-quartet]] — the firm-level binding constraints.
- [[ai-skill-shortage-as-diffusion-bottleneck]] — the worker-level binding constraint.
- [[autonomy-slider]] — why human-in-the-loop requirements slow deployment.
- [[task-based-framework]] — macro envelope the gap-closing operates inside.
- [[H2_u-curve-of-value]] — the value-stack consequence: surplus accrues to capital owners of the deployed application layer as the gap closes.
- [[capital-labor-divergence]] — the labor-incidence consequence.
- [[ai-productivity-firm-level]] — productivity link contingent on the gap closing at firm level.
