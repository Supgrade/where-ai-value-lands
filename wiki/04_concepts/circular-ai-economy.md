---
title: The Circular AI Economy
status: emerging
tags:
  - concept
  - economics
  - capex
  - revenue
  - bear-case
last-updated: 2026-05-21
---

# The Circular AI Economy

> [!abstract] One-line
> The claim that **current AI "revenue" is largely VC capital pass-through** flowing in a closed loop from venture funds → application startups → foundation models → hyperscalers, with very little net-new non-tech enterprise revenue entering the system.

## The loop
1. **VC** funds application-layer startups (Cursor, Perplexity, etc.) at high valuations.
2. **Startups** immediately spend most of their cash on API calls to foundation models. Many spend **>100% of revenue on compute** — Perplexity reportedly ~164% of revenue in 2024.
3. **Foundation models** (OpenAI, Anthropic) spend the bulk of their incoming revenue on hyperscaler compute. OpenAI reportedly ~50% on [[inference]] + ~75% on training.
4. **Hyperscalers** book this cash as "AI revenue" on earnings calls, justifying the next leg of capex.
5. **~70–80%** of Microsoft/AWS AI capacity is consumed by **just two customers**: OpenAI and Anthropic.
6. Meanwhile, foundation models build downstream products (Claude Code, ChatGPT apps) that **cannibalize their own application-layer customers**, accelerating their burn.

The result: a financial ouroboros sustained by external venture capital injections rather than by net new utility being purchased by non-tech enterprises at sustainable prices.

## The capex side
- Hyperscaler capex over 3 years: **~$800B**.
- Planned additional capex 2026–2027: **~$1.7T**.
- Estimated AI-specific net-new revenue required just to **break even**: ~$3T.
- For a normal tech-sector ROI: **~$6T+**.
- Combined annual revenue of MSFT + META + AMZN + GOOG (all products): **~$1.599T**. The required AI line item would have to **dwarf** the entire current business of the four largest tech companies combined.

## What goes wrong when (not if) the music stops
- Macro tightens → VC funding to application startups slows.
- Application startups, with inverted unit economics, collapse first.
- Foundation models' API revenue cliffs.
- Hyperscalers are left with **rapidly depreciating specialized hardware** (GPU half-life is short relative to traditional servers) and **stranded municipal power contracts**.
- The "AI revenue" line item that justified the capex disappears in two quarters.

## Physical caps reinforcing the financial caps
Even if the financial loop didn't break, **energy and grid constraints** physically cap deployment. US utilities are facing demand surges they haven't seen in nearly two decades, against an aging grid. Grid expansion involves regulatory friction, supply-chain bottlenecks, and large municipal capital outlays. The "Moore's Law for inference" assumption that AI compute will deflate aggressively is contradicted by the physics of energy, cooling, and real estate. See [[goldman-sachs-too-much-spend]].

## Why this matters for [[H2_u-curve-of-value]]
This concept is the single most direct threat to the U-curve. The U assumes value concentrates at the **bottom** of the stack (silicon, energy, weights). The circular-economy thesis argues that the bottom is currently propped up by recycled VC capital, not durable enterprise demand. If the bottom is hollow, the shape is not a U — it could be an **upside-down U**, an **L** (only the top survives), or a **flat-line collapse** under correction.

## Why this might be wrong
- Snapshot-in-time critique. Compute costs are falling rapidly per unit of capability; enterprise adoption curves typically lag by years; SaaS unit economics took a decade to settle.
- Hyperscaler "AI revenue" is partly compute *also* used for non-AI workloads (search, recommendations, internal use) — the ouroboros may be smaller than the headlines suggest.
- The concentration of capacity in OAI + Anthropic could be a transient market structure, not a permanent feature.
- Some enterprise revenue is real and growing (Microsoft Copilot seats, ServiceNow GenAI SKUs); the question is the *rate*, not the existence.

## Open questions
- What is the **actual** ratio of VC-recycled compute spend to real enterprise spend? Triangulating from public filings is hard but possible.
- How much hyperscaler capex is **fungible** (general compute) vs. **AI-specific** (specialized inference / training hardware)? Fungibility determines downside.
- Are there application-layer winners (vertical or platform-tier) breaking the inverted-margins pattern? If so, the U may yet hold above some threshold.

## Data
- [[hyperscaler-capex-trajectory]] — $800B booked + $1.7T planned.
- [[hyperscaler-customer-concentration]] — 70–80% of capacity → OpenAI + Anthropic.
- [[perplexity-burn-ratio]] — ~164% of revenue to compute (2024).

## Related
- [[zitron-circular-economics]]
- [[goldman-sachs-too-much-spend]]
- [[bear-case-synthesis]]
- [[H2_u-curve-of-value]]
- [[H1_L0-L7-ladder]]
- [[wef-ai-in-action-2025]] — bull counterpart that does not engage with the circularity question; assumes the $632B spend trajectory will produce durable enterprise demand.
