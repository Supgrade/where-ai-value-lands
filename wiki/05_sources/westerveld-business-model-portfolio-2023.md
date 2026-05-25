---
title: "Westerveld et al. — The Business Model Portfolio as a Strategic Tool (2023)"
status: ingested
tags:
  - source
  - business-models
  - strategy
  - portfolio
  - paradox-theory
last-updated: 2026-05-25
---

# Westerveld et al. — The Business Model Portfolio as a Strategic Tool

## Citation

Westerveld et al. (2023). **The Business Model Portfolio as a Strategic Tool for Value Creation: Opportunities and Paradoxes.** *Journal of Strategy and Management*. Developmental literature review (Templier & Paré 2015) + Gioia methodology coding over 38 empirical case studies, databases screened 2010–2021.

Ingested in the wiki as a **recap document**, not the full paper — the source file in `raw/` is a structured 63-line summary of central thesis, evidence, critical evaluation, and methodological assessment.

## Central claim

> Operating multiple business models — a **Business Model Portfolio (BMP)** — has evolved from a defensive contingency strategy into a **proactive strategic tool for value creation**. Modern firms cannot rely on a single monolithic BM; they must harmonise diverse, often interdependent BMs to leverage demand-side and supply-side synergies. This strategic pluralism is inherently paradoxical — value opportunities and organisational tensions are co-produced and cannot be solved, only managed.

The paper's principal contribution to *this* project is operational: it provides the **prerequisite scoping rule** — *the BM, not the firm, is the unit of strategic analysis* — that makes the [[weber-ai-startup-business-models]] classifier work for multi-BM AI startups. See [[business-model-portfolio]] for the concept page that grounds this rule.

## Key arguments

### 1. The three strategic intents (chronological)

- **Diversifying** — autonomous BMs targeting distinct market segments (legacy airline + low-cost carrier). Historically dominant.
- **Sensing** — BMs as experimental probes; failed probes are discarded without disrupting the core. Aligns with the "thousand flowers bloom" phase in [[wef-ai-in-action-2025]] and the early stages of [[enterprise-adoption-ladder]].
- **Complementing** — tightly integrated BMs where one reinforces another via shared data and functional architecture (Amazon Prime ↔ retail ↔ streaming; LAN Airlines passenger ↔ cargo). The most advanced contemporary intent.

Synthesis observation in the recap: the Complementing intent strongly aligns with Huang's "extreme co-design" in [[karpathy-software-3]], where a computing platform's survival is dictated by its integrated install base across applications.

### 2. Digital technology as connective tissue

Digitalisation is the *primary catalyst* enabling modern BMPs. Customer data captured in one BM can power the value proposition of another; shared functional architecture lets supply-side synergies cross BM boundaries. The recap cites GoMore (car-sharing data matching car-leasing supply) and omnichannel retailers (online data informs offline value proposition).

The recap explicitly extends this to AI: the Deloitte AI Dossier's "multi-agent AI ecosystems" ([[deloitte-ai-dossier-eri]]) are the 2026 mechanism through which the functional-architecture-as-bridge claim is currently being realised.

### 3. The four BMP paradoxes (permanent, not solvable)

- **Horizon paradox** (exploit vs explore) — anchored in March (1991) ambidexterity / exploitation-exploration framework.
- **Cannibalization paradox** — new BM captures revenue from the incumbent. In 2026 AI: Steinberger's GUI-vs-agent-API thesis in [[karpathy-software-3]] is the canonical instance.
- **Digital paradox** — physical vs digital asset tension; omnichannel complexity vs customer's desire for seamlessness.
- **Dogmatic paradox** — organisational confirmation bias toward the incumbent. Echoed by Sutskever's "human reward hacking" in [[eval-real-world-gap]]: researchers (and managers) over-optimise current recipes rather than seek contradictory evidence.

### 4. Theoretical scaffolding

- **Business Model concept** (Massa et al. 2017; Teece 2010) — Value Proposition / Value Architecture / Functional Architecture / Financial Sustainability — used as the structural taxonomy.
- **Paradox Theory** (Smith & Lewis) — tensions as "contradictory yet interrelated elements" requiring dynamic equilibrium, not resolution.
- **Ambidexterity / Exploitation-Exploration** — underpins the Horizon paradox.

## Method

- Developmental literature review (Templier & Paré 2015) + Gioia methodology (1st-order / 2nd-order coding, abductive transition).
- Databases screened **2010–2021**.
- Final sample: **38 highly relevant empirical case studies**.

## Critical evaluation

- **Retrospective constraint** — the 38 cases were *not originally designed* to investigate BMPs or paradoxes; opportunities and tensions are extracted through post-hoc interpretive coding. Risk of uneven focus.
- **Industry and geographic bounding** — sample concentrated in airlines, media, retail; lacks deep coverage of heavy / asset-intensive sectors (deep-tech manufacturing, nuclear energy), so hardware / regulatory paradox classes may be missing.
- **Pre-LLM cutoff** — the literature window closes in 2021. The recap's AI-era extensions (Karpathy, Sutskever, Steinberger, Huang, WEF, Deloitte) are *interpretive bridges added by the recap author*, not findings of the original paper.

## Hypothesis touches

- **[[H1_L0-L7-ladder]]** — neutral. The BMP frame operates orthogonally to the ladder; a startup can sell BMs at different ladder positions.
- **[[H2_u-curve-of-value]]** — modest reinforcement. A single firm can run one BM at the top of the U (a [[distribution-moat]]-backed product) and another at the shoulder (services, analytics) — explains why empirical firm-count data is messier than the value-capture claim.
- **[[H3_orthogonal-axes-under-priced]]** — direct reinforcement. The BMP frame is the structural reason a single firm occupies multiple positions on every analytical axis, which is exactly the situation H3 names as under-priced.
- **[[H4_rl-specialization-value-pocket]]** — neutral. H4 is a per-BM claim; the BMP frame clarifies that an H4 BM can coexist with non-RL BMs in the same firm.

## Open questions surfaced

- Does the *Complementing* intent dominate the Diversifying / Sensing intents in 2026 AI specifically, or is the AI-startup mix still Sensing-heavy (per [[wef-ai-in-action-2025]] "thousand flowers")?
- Of the four paradoxes, which is most salient for AI startups specifically? The recap argues *Cannibalization* (Steinberger thesis) and *Dogmatic* (Sutskever thesis); evidence in the wiki is thin.
- Does the BMP frame transfer cleanly to small / early-stage firms, or is it primarily an incumbent / scale-up phenomenon? Westerveld's 38 cases are biased toward incumbents.

## See also

- [[business-model-portfolio]] — the concept page grounded in this source; carries the unit-of-analysis claim into the wiki.
- [[weber-ai-startup-business-models]] — the classifier this source is prerequisite to.
- [[ai-startup-business-archetypes-weber]] — the operational classifier; applied per-BM in light of the BMP frame.
- [[weber-taxonomy-2026-gaps]] — the diagnostic page that now opens with the BMP prerequisite framing.
- [[H2_u-curve-of-value]] · [[H3_orthogonal-axes-under-priced]] — the hypotheses most affected by the BMP frame.
- [[karpathy-software-3]] — Huang's extreme co-design ↔ Complementing intent; Steinberger ↔ Cannibalization paradox.
- [[eval-real-world-gap]] · [[sutskever-age-of-research]] — Sutskever's "human reward hacking" ↔ Dogmatic paradox.
- [[wef-ai-in-action-2025]] · [[enterprise-adoption-ladder]] — thousand-flowers-to-enterprise-reinvention arc ↔ Sensing-to-Complementing arc.
- [[deloitte-ai-dossier-eri]] — multi-agent ecosystems as the 2026 enactment of functional-architecture-as-connective-tissue.
- [[digital-core]] — buyer-side mirror of the connective-tissue claim.
