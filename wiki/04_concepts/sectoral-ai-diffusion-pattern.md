---
title: Sectoral AI Diffusion Pattern
status: concept
target_folder: wiki/04_concepts/
tags:
  - adoption
  - sectoral
  - diffusion
  - empirical
last-updated: 2026-05-22
---

# Sectoral AI Diffusion Pattern

> **AI use is concentrated where AI is made.** In 2024, ~45% of firms in the ICT sector and ~26% in Professional, scientific & technical activities used AI across OECD countries — three to six times the adoption rate of Construction (7.2%), Accommodation & food services (7.8%), or Transportation & storage (9.2%). The ICT sector also scores top-quartile on every dimension of *AI intensity* (human capital, innovation, exposure, use). Source: [[oecd-sme-ai-adoption-2025]].

This is the **sectoral compounding factor** behind the [[sme-ai-adoption-gap]]. Even comparing firms of similar size and age, sectoral composition shifts adoption rates by a multiple.

## The pattern

Three concentric layers:

1. **AI-intensive sectors.** ICT (Media, IT services, Telecommunications), Scientific R&D, Legal & accounting, Finance & insurance. Top-quartile across all four AI-intensity dimensions in the Calvino et al. (2024) sectoral taxonomy.
2. **Mid-intensity sectors.** Manufacturing of transport equipment, machinery, computer & electronics; Wholesale & retail. Second or third quartile. AI-relevant but not AI-native.
3. **Low-intensity sectors.** Construction, Hotels & food services, Textiles, Wood & paper, Transportation & storage. Bottom-quartile across most dimensions. These are the bulk of the SME population in OECD economies.

The same hierarchy holds in every G7 country: **ICT adoption rates are typically more than 3× manufacturing's**.

## What "AI intensity" packages together

The Calvino et al. multidimensional indicator distinguishes:

- **AI human capital** — share of workers in AI-relevant occupations.
- **AI innovation** — patents and publications in the sector.
- **AI exposure (barrier-adjusted)** — share of tasks technically exposed to AI, weighted by adoption barriers.
- **AI use** — share of firms adopting.

The four scores correlate but are not identical. **ICT and IT services score top-quartile on all four** — they make the technology, adopt it earliest, and have the workers to deploy it. **Manufacturing sub-sectors are split**: Computer & electronics is top-quartile, transport equipment / machinery is middle, food / textile / wood is bottom. The decomposition lets us see that "manufacturing" as a single category hides a 3–4× internal range.

## The good news

The increase is an **all-sector phenomenon**. Between 2021 and 2024, OECD-wide adoption **roughly doubled** in most sectors:

- ICT: +20 percentage points (from ~25% to ~45%)
- Professional services: +13 pp
- Wholesale trade: +8 pp
- Manufacturing: ~+5 pp (a 70% relative increase from a low base)
- Transportation & storage: ~+3.5 pp (a 60% relative increase)

The largest absolute increases are in already-high-adoption sectors — i.e., **the sectoral gap is widening in absolute terms even as it narrows in relative terms**. ICT pulled away from manufacturing by ~15 pp in three years.

## Why this matters for the U-curve

- **The "long-tail application layer" is concentrated in low-intensity sectors.** If the bottom-right of [[H2_u-curve-of-value]] is "SMEs in construction, hospitality, transport, retail" — the literal majority of European economic activity by employment — those sectors are at single-digit AI adoption rates. The U's bottom-right is **thin where the population is thickest**.
- **The "shaping" sectors are also the producing sectors.** Calvino et al. note that ICT and professional services are simultaneously the largest adopters and the largest *suppliers* of AI. This is a recursion: the part of the economy that captures most AI surplus today is the part that builds the technology. This is consistent with the [[capital-labor-divergence]] story — value flows from the rest of the economy into the AI-producing sector via vendor relationships.
- **Diffusion S-curve.** Per [[diffusion-vs-innovation]], the GPT winner is whoever absorbs the technology fastest across all productive sectors. The sectoral pattern shows the OECD is still early on that curve — manufacturing, construction, and transport are at the bottom of the S.

## Tensions

- **Sector-mix vs sector-effect.** Larger firms tend to be in different sectors than smaller firms; some of the [[sme-ai-adoption-gap]] is a sector compositional effect. But OECD work (Calvino & Fontanelli 2023) shows the size gap persists *within* sector — sector is a compounding factor, not the full explanation.
- **AI intensity ≠ AI value-capture.** The Computer & electronics sector scores top-quartile on use and intensity, but its margin profile is not obviously richer than Media or IT services. The sectoral taxonomy measures adoption, not capture.
- **Definitions drift.** "AI use" in 2021 surveys covers a narrower technology set than "AI use" in 2024 surveys (generative AI is the most striking addition). Trend comparisons should be read with this in mind.

## Related

- [[oecd-sme-ai-adoption-2025]] — primary source.
- [[sme-ai-adoption-gap]] — the inter-firm gap this sectoral pattern compounds.
- [[oecd-sectoral-ai-adoption-2024]] — the data block behind this concept.
- [[diffusion-vs-innovation]] — the diffusion-S-curve framing.
- [[H2_u-curve-of-value]] — the U's bottom-right is thin where the population is thickest.
- [[capital-labor-divergence]] — surplus flow from low-intensity sectors to AI-producing sectors.
- [[vertical-ai-orchestration]] — what a successful sectoral-AI deployment looks like in industrial verticals.
- [[deloitte-ai-dossier-eri]] — the ER&I instantiation of this pattern.
- [[ai-productivity-firm-level]] — the productivity link this concept sits inside.
