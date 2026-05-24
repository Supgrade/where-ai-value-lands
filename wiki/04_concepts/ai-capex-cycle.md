---
title: AI Capex Cycle
status: working
tags:
  - concept
  - capex
  - infrastructure
  - bear-case
  - economics
last-updated: 2026-05-23
---

# AI Capex Cycle

The hyperscaler capital-expenditure boom-then-bust pattern that defines the bottom of the AI stack as a financial object: **massive training capex now → uncertain inference demand later → potential overcapacity and write-downs if enterprise revenue lags**. The cycle is the central mechanism of the [[bear-case-synthesis]] applied to infrastructure: even granting that AI value is real, the *timing* between when GPUs are bought and when durable enterprise demand materialises is wide enough to put the bottom of [[H2_u-curve-of-value]] at risk. The concept is structural rather than purely cyclical — depreciation curves on AI-specialised hardware are short, and stranded power contracts are long.

## The boom-to-bust mechanism

The boom phase is documented in [[hyperscaler-capex-trajectory]]: ~$800B of hyperscaler capex booked over three years, with ~$1.7T more planned for 2026–2027. The cumulative bet requires roughly **$3T of net-new AI-specific revenue to break even and $6T+ for normal tech-sector ROI** — figures that dwarf the combined annual revenue of MSFT + META + AMZN + GOOG (~$1.6T across all current products). The bust mechanism, articulated most sharply by [[zitron-circular-economics]] and [[goldman-sachs-too-much-spend]], is a chain rather than a shock:

1. The training-capex line item assumes inference demand will scale to absorb the installed base.
2. ~70–80% of that installed base is currently consumed by two customers — OpenAI and Anthropic ([[hyperscaler-customer-concentration]]) — themselves dependent on VC capital pass-through and inverted-margin application-layer customers ([[perplexity-burn-ratio]]). See [[circular-ai-economy]] for the closed loop.
3. If macro tightens or VC funding slows, the application layer collapses first; foundation-model API revenue cliffs; the hyperscaler "AI revenue" line that justified the next capex round disappears in two quarters.
4. The residual is **rapidly depreciating specialised hardware** (AI-GPU half-life is short relative to traditional servers) and **stranded municipal power contracts and grid connections**. Write-downs follow. Covello at Goldman compounds this with physical caps — utility build-out, grid expansion, regulatory friction — that constrain the deployment side regardless of financial appetite.

## Why this is the central bear-case mechanism

The cycle is the **single most direct threat to the bottom of [[H2_u-curve-of-value]]**. The U-curve relies on substrate scarcity (silicon, energy, frontier weights) producing durable margin; the capex-cycle thesis argues that this apparent scarcity is currently *priced* by recycled VC, not by net-new enterprise demand. If correct, the U is upside-down or collapses to an L (only the top survives). The bull counter ([[jevons-paradox-ai]], [[ai-factory-huang]], [[karpathy-software-3]]'s "intelligence on tap") argues that efficiency gains expand total compute demand rather than contracting it and that gigawatt-scale [[ai-factory-huang]] economics make the substrate a utility, not a speculative bet — partially restoring the bottom against the cycle thesis but not dispositively. The unsettled position the wiki holds: the capex cycle is real, its trigger is uncertain, and the downside is asymmetric in time (rapid revenue cliff vs slow asset depreciation, with power and grid commitments locked in throughout). For SMEs and non-tech enterprises, the cycle matters because the platforms they rent AI from sit downstream of it; a hyperscaler correction reprices the entire [[application-layer]] above.

## Related

- [[circular-ai-economy]] — the financial loop this concept sizes; closely overlapping but framed by *time* rather than *flow*.
- [[hyperscaler-capex-trajectory]] — the $800B + $1.7T data point.
- [[hyperscaler-customer-concentration]] — 70–80% of capacity → OpenAI + Anthropic; the demand-side fragility.
- [[zitron-circular-economics]] — primary source for the bust mechanism.
- [[goldman-sachs-too-much-spend]] — middle-of-the-market skeptic on the same trajectory; physical caps.
- [[bear-case-synthesis]] — the cluster this concept anchors.
- [[H2_u-curve-of-value]] — the direct threat to the bottom of the U.
- [[ai-factory-huang]] — bull-frame counter; the capex *is* the manufactured-intelligence asset.
- [[jevons-paradox-ai]] — efficiency-expands-demand counter that partially defends the bottom.
- [[task-based-framework]] — macro envelope; if surplus is small, the capex is overbuilt regardless of cycle timing.
- [[application-layer]] — what gets repriced if the capex cycle corrects.
- [[value-capture]] — wedge between value created by infrastructure and value retained after a correction.
- [[scaling-wall]] — capability-side risk that compounds the demand uncertainty.
- [[karpathy-software-3]] — bull-frame paradigm document that treats the substrate as load-bearing rather than over-extended.
