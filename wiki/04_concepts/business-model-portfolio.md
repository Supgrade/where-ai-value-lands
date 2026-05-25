---
title: Business Model Portfolio
status: established-framework
tags:
  - concept
  - business-models
  - strategy
  - unit-of-analysis
last-updated: 2026-05-25
---

# Business Model Portfolio

A **Business Model Portfolio (BMP)** is the set of distinct, often interdependent, business models a single firm operates simultaneously. Source: [[westerveld-business-model-portfolio-2023]] (Westerveld et al., 2023 — developmental literature review over 38 empirical cases, 2010–2021).

The core move is to treat *the business model*, not *the firm*, as the unit of strategic analysis. A startup may *be* one company on the cap table while *running* two or three business models, each with its own value proposition, value architecture, functional architecture, and revenue logic. Operating multiple BMs has shifted from a defensive contingency (diversification against shocks) to a **proactive strategic tool** for value creation — and a permanent source of organisational paradox.

> [!key] Why this page exists in this wiki
> The [[weber-ai-startup-business-models]] classifier and the [[ai-startup-business-archetypes-weber]] morphological box silently assume **one startup = one business model**. In practice, especially in 2026, AI startups routinely run two or more BMs (e.g. a self-serve B2C product *and* an enterprise consulting engagement *and* a developer API). Without the BMP frame, a single startup is forced into one Weber pattern that distorts the picture. With the BMP frame, **each BM is classified separately**, and Weber's four-pattern taxonomy becomes a per-BM, not a per-firm, instrument. This page is the prerequisite framing for [[weber-taxonomy-2026-gaps]] and the planned GTM sibling taxonomy.

## Three strategic intents (chronological evolution)

Westerveld et al. identify a chronological shift in *why* firms deploy a BMP:

1. **Diversifying** — historically dominant. Different BMs target distinct market segments autonomously (e.g. a legacy airline operating a separate low-cost carrier). Logic: hedge.
2. **Sensing** — BMs as experimental probes into uncertain markets. Failed probes are discarded without disrupting the core. Logic: option value. Maps to "thousand flowers bloom" phase in [[wef-ai-in-action-2025]] and to the early experimentation tier of [[enterprise-adoption-ladder]].
3. **Complementing** — the most advanced contemporary intent. Tightly integrated BMs where one explicitly reinforces another via shared data, infrastructure, or audience (Amazon Prime ↔ retail ↔ streaming; LAN Airlines passenger ↔ cargo capacity sharing). Logic: ecosystem synergies. Aligns with Huang's "extreme co-design" in [[karpathy-software-3]] and with the "enterprise-level reinvention" tier of [[enterprise-adoption-ladder]].

**Digital technology and data are the connective tissue** that makes *Complementing* feasible at scale. Customer data captured in one BM can power the value proposition of another; shared functional architecture lets supply-side synergies cross BM boundaries.

## Four paradoxes (permanent, not solvable)

Operating a BMP is "an exercise in balancing dualities". Westerveld et al. identify four persistent tensions that cannot be eliminated, only managed:

- **Horizon paradox** (Exploit vs Explore) — the most prevalent. Exploit profitable capabilities while funding unproven ones. Theoretical anchor: ambidexterity / March 1991. In AI startups: maintaining a paying enterprise BM while staffing an experimental agent product.
- **Cannibalization paradox** — the new (often digital, often agentic) BM threatens to capture revenue from the incumbent BM. In 2026 AI: Steinberger's prediction in [[karpathy-software-3]] that agent-facing APIs will cannibalise GUI-led SaaS is the canonical instance.
- **Digital paradox** — tension between physical and digital assets, and between omnichannel complexity and the customer's desire for seamlessness.
- **Dogmatic paradox** — organisational confirmation bias toward the incumbent BM. Echoed in AI research by Sutskever's "human reward hacking" in [[eval-real-world-gap]]: researchers (and managers) over-optimise current recipes rather than seeking contradictory evidence.

## Implication for the project

1. **Unit of analysis.** When ingesting an AI-startup source, identify *each BM the startup operates* before applying [[ai-startup-business-archetypes-weber]]. Classify per-BM. Record in the source frontmatter as `weber-pattern: <pattern>` per BM if more than one.
2. **Strategic separation.** For an operator (the author's audience): keep each BM's value proposition, distribution architecture, and pricing logic *deliberately separate* even when run by the same team. The logics are diverse; conflating them is the most common source of cannibalisation pain.
3. **Strand B link.** The forthcoming GTM sibling taxonomy ([[weber-taxonomy-2026-gaps]] *Next move*) will inherit BMP framing: each BM gets its own commercialisation motion, channel geometry, and pricing counterparty. A startup with two BMs has two GTM motions to track.
4. **IT / digital strategy as enterprise matrix.** Westerveld's strongest practical implication: in a BMP, functional architecture (data, infrastructure, AI) cannot be aligned to a single BM. It is the connective tissue. The digital-core argument in [[digital-core]] is the buyer-side mirror of this point.

## What this page is not

- Not a replacement for Weber. It is the **prerequisite scoping rule** that makes Weber applicable to multi-BM firms.
- Not a planning template. The three intents and four paradoxes are diagnostic vocabulary, not a checklist.
- Not validated on AI startups specifically. Westerveld's 38 cases are airlines, retail, media — sectors with long-running BMP histories. The 2026 AI-startup application is an extrapolation this wiki is making.

## See also

- [[westerveld-business-model-portfolio-2023]] — the source.
- [[ai-startup-business-archetypes-weber]] — Weber's classifier; the BMP frame is the unit-of-analysis prerequisite.
- [[weber-ai-startup-business-models]] — the source taxonomy.
- [[weber-taxonomy-2026-gaps]] — the diagnostic this page sits in front of.
- [[H3_orthogonal-axes-under-priced]] — a startup running multiple BMs occupies multiple positions on every analytical axis; the BMP frame is the structural reason orthogonal axes matter.
- [[H2_u-curve-of-value]] — a single startup can have one BM at the top of the U and another at the shoulder.
- [[karpathy-software-3]] — Huang's "extreme co-design" as the Complementing intent in computing; Steinberger's GUI-vs-agent thesis as the Cannibalization paradox in 2026.
- [[eval-real-world-gap]] — Sutskever's "human reward hacking" as the Dogmatic paradox in AI research.
- [[digital-core]] — buyer-side mirror of the "functional architecture as connective tissue" claim.
- [[enterprise-adoption-ladder]] — the WEF ladder maps loosely onto the Sensing → Complementing intent progression.
- [[wef-ai-in-action-2025]] — "thousand flowers bloom" → "enterprise-level reinvention" as the WEF reading of the same Sensing → Complementing shift.
