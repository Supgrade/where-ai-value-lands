---
title: The Scaling Gap (74% / 16%)
status: concept
tags:
  - adoption
  - empirical
  - middle-dies
last-updated: 2026-05-22
---

# The Scaling Gap

> **74% of companies report challenges in adopting AI at scale; only 16% of enterprises are prepared for AI-enabled reinvention.** (BCG / Accenture, 2024, via [[wef-ai-in-action-2025]])

The empirical gap between AI *investment* (surging — $632B projected by 2028) and AI *value-capture inside the enterprise* (shallow — most firms stuck in Phase 1–2 of the [[enterprise-adoption-ladder]]).

## Why it matters to this paper

The gap is interpretation-flexible. Three readings of the same number:

1. **Managerial reading (WEF / Accenture stance).** The 84% gap is a *sequencing* problem. Foundational enablers ([[foundational-enablers]]) — governance, talent, digital core — are missing. Once enterprises put them in place, scaling completes. The gap is closeable through better practice.

2. **Bear reading (compatible with [[bear-case-synthesis]]).** The 84% gap is structural evidence that enterprise AI does not deliver on its promise at the use-case level. If most firms cannot scale, the marginal value of AI per dollar of investment is much lower than the bull projections imply. Compatible with [[circular-ai-economy]] (revenue is recycled VC) and with [[task-based-framework]]'s <0.71% TFP cap.

3. **Middle-dies reading (compatible with [[H2_u-curve-of-value]]).** The 84% gap is enterprise-side evidence for the [[middle-layer-defensibility]] story: most internal AI initiatives are "thin wrappers" applied to existing workflows without owning the distribution layer or the substrate. They die for the same reason mid-stack vendors die — undifferentiated, capital-hungry, no moat. Only firms that *already* own distribution or proprietary data (the case studies in [[wef-ai-in-action-2025]]: LSEG, BMW, AT&T, Chevron) successfully scale.

The three readings are not mutually exclusive. The same gap can be evidence for all three pressures operating at once.

## A parallel worker-level gap

The 74% enterprise gap has an **occupation-level twin**: [[theoretical-vs-observed-capability-gap]] from [[massenkoff-mccrory-labor-market-impacts-2026]]. In the most-exposed occupational category (Computer & Math), LLM **theoretical capability covers 94% of tasks** but **observed Claude work-context usage covers only ~33%**. The same diffusion-lag pattern recurs at a different unit of analysis. The two gaps are sibling phenomena of [[diffusion-vs-innovation]] — capability outruns deployment everywhere it is measured.

The two are not redundant evidence; they measure different things. The enterprise gap is **intra-firm scaling difficulty** (firms have started but can't scale); the occupational gap is **task-level deployment shortfall** (capability exists but isn't being used in work). They compound: an enterprise that cannot scale AI will leave its workers' theoretically exposed tasks unautomated, lengthening the occupational gap.

## Mechanisms / SME-specific evidence

The BCG / Accenture survey reports the gap but not its mechanism. The OECD G7 paper ([[oecd-sme-ai-adoption-2025]]) supplies the SME-level mechanism: pilots fail to scale not because the model is wrong, but because the adopting firm lacks the workforce capacity to operate and adapt it. Three concrete SME-side bottlenecks compound:

- **Skills.** 50%+ of SMEs in four G7 countries report employees lack the skills to use generative AI; under 30% of gen-AI-using SMEs provide any AI-related training, and as low as 11.3% in Japan (see [[ai-skill-shortage-as-diffusion-bottleneck]]).
- **Finance.** Tightening credit conditions since 2022 have shifted SME finance composition toward short-term lending — exactly the wrong shape for multi-year AI integration (see [[sme-ai-finance-gap]]).
- **Connectivity.** A flat 25-pp small-vs-large firm broadband gap caps the infrastructure ceiling under which scaling can happen (see [[sme-connectivity-divide]]).

These mechanisms map onto the OECD adopter taxonomy: SMEs stall transitioning from Novice → Optimiser, and from Optimiser → Explorer, because the next stage requires new capabilities the firm has not yet built. The scaling gap is not a software problem; it is an absorptive-capacity problem.

## What it does not tell us

- *Why* the 74% struggle. The survey reports the gap, not its mechanism.
- Whether the gap is *closing* over time or stable.
- Whether the 16% that scale capture *durable* value or vendor-relationship-dependent value.
- Whether the failures are concentrated in any specific stack layer (the survey is not stratified by where in the [[H1_L0-L7-ladder]] the failed initiatives sat).
- **It is silent on firm size.** The BCG / Accenture 74% figure is **not stratified by firm size**, and the underlying survey is heavily weighted toward large firms. [[oecd-sme-ai-adoption-2025]] documents a separate, structural [[sme-ai-adoption-gap]] (40% large vs 11.9% small firms adopting AI OECD-wide in 2024). The two gaps are **different denominators**: the 74% measures *intra-firm* failure to scale among firms that have already started; the SME gap measures *inter-firm* failure to start. They likely **compound** — most SMEs do not even reach the pilot stage the BCG figure measures, so the "74% stuck" is a conservative read of total enterprise-side friction.

## Sources

- Primary: [[wef-ai-in-action-2025]] reporting BCG / Accenture surveys.
- BCG Global, October 2024: "AI Adoption in 2024: 74% of Companies Struggle to Achieve and Scale Value."
- Accenture, 2024: "Accelerating reinvention to support growth with AI-powered operations."

## Data

- [[scaling-gap-74-16]] — the keystone 74% / 16% figure, with citation chain.

## Related

- [[wef-ai-in-action-2025]] — source.
- [[enterprise-adoption-ladder]] — the 5-phase ladder the gap sits inside.
- [[foundational-enablers]] — what WEF claims closes the gap.
- [[H2_u-curve-of-value]] — middle-dies reading.
- [[middle-layer-defensibility]] — the structural lens.
- [[bear-case-synthesis]] — bear reading.
- [[circular-ai-economy]] — bear mechanism.
- [[task-based-framework]] — bear cap on the surplus.
- [[distribution-moat]] — what the 16% that scale tend to already own.
- [[oecd-sme-ai-adoption-2025]] — supplies the inter-firm gap that compounds with the 74%, and the SME-side mechanisms.
- [[sme-ai-adoption-gap]] — the SME-vs-large dimension.
- [[oecd-sme-adopter-taxonomy]] — visualizes an SME analogue of the pilot-to-scale gap at the Functional→Cross-functional boundary.
- [[ai-skill-shortage-as-diffusion-bottleneck]] — skills mechanism.
- [[sme-ai-finance-gap]] — finance mechanism.
- [[sme-connectivity-divide]] — infrastructure mechanism.
- [[massenkoff-mccrory-labor-market-impacts-2026]] — occupation-level sibling gap.
- [[theoretical-vs-observed-capability-gap]] — worker-level diffusion-lag twin.
- [[observed-exposure-measure]] — the measurement instrument exposing the worker-level gap.
- [[ml-monitoring]] — a third reading of the gap, complementary to bull-managerial and bear-capability readings: pilots scale poorly *also* because the monitoring infrastructure that catches silent production degradation is systematically under-budgeted. [[protschky-ml-monitoring-2025]]'s 17-practice surface is the operational bill of materials most pilots don't pay for.
- [[ml-monitoring-quality-cycle]] — the surface most pilots under-implement.
- [[protschky-ml-monitoring-2025]] — empirical anchor for the operational-root-cause reading.
- [[H5_ai-as-operational-not-product]] — interpretation-flexible support: the 26%/84% who scale capture the differential, which is exactly the operator-track surplus H5 is built on (with the caveat that the gap may be structural rather than executional).
