---
title: Protschky et al. (2025) — What Gets Measured Gets Improved
status: draft
tags:
  - source
  - monitoring
  - mlops
  - software-engineering
  - production
  - peer-reviewed
last-updated: 2026-05-25
---

# Protschky et al. (2025) — What Gets Measured Gets Improved: Monitoring Machine Learning Applications in Their Production Environments

## Citation

Protschky, D., Lämmermann, L., Hofmann, P., & Urbach, N. (2025). *What Gets Measured Gets Improved: Monitoring Machine Learning Applications in Their Production Environments*. **IEEE Access, 13**, 34518–34530. DOI: [10.1109/ACCESS.2025.3534628](https://doi.org/10.1109/ACCESS.2025.3534628). Open access (CC BY 4.0). Received 1 Dec 2024, accepted 7 Jan 2025, published 13 Feb 2025.

**Affiliations:** Fraunhofer Institute for Applied Information Technology (FIT, Bayreuth, Germany), University of Bayreuth, FIM Research Center for Information Management (Bayreuth), appliedAI (Munich).

## Central claim

ML applications fail in production in ways that conventional software does not, because of five structural characteristics of their production environment (C1–C5). Existing MLOps literature streamlines workflow automation but provides "little guidance" on monitoring. The paper derives **17 monitoring practices**, arranged on a five-step quality-management cycle (define / measure / assess / act / control) + 3 cross-sectional, that operationalise ML monitoring as a discipline distinct from software monitoring.

## Method

Qualitative mixed-method (Figure 2):

1. **Multivocal literature review.** 25 academic articles (IEEE Xplore, ACM, arXiv search on "machine learning AND monitoring") + 56 practitioner articles (Medium, towardsdatascience, vetted with Garousi et al.'s grey-literature quality framework + backward-search). Initial sample 5,887 + 399 + 1,473 articles.
2. **Interview study.** 10 semi-structured interviews (Myers & Newman; Schultze & Avital methodology) with senior data scientists, ML engineers, heads of data science, ML monitoring CEOs across Software, Healthcare, Energy, Consulting, Retail in DE / USA / India / Australia / Italy. Coding via Corbin & Strauss + Saldaña, yielding 385 codes / 31 categories. Saturation declared after interview 10.
3. **Monitoring-tool review.** 15 ML monitoring tools (denoted T01–T15) reviewed via documentation + public materials. Used to enrich practices with lessons from real tooling *and* to identify gaps that the practices fill but the tooling doesn't.

Triangulation across the three data sources is the paper's main rigor claim.

## Key contributions (the artefacts the wiki cares about)

### The two-layer framework (Figure 1)

An ML application in production sits between a **representation layer** (training data, features, model, output, metadata) and a **real-world layer** (the phenomenon the system is supposed to be about). The two communicate through eight measurement areas: agents (1), input data (2), preprocessing/storing (3), metadata (4), algorithm (5), output (6), task (7), business value (8). Infrastructure (4 area in the diagram) is the substrate. **Monitoring is the entity that observes the real-world layer through the representation layer.** The operational version of [[eval-real-world-gap]]: the eval lives in the representation layer; the real-world layer is what bites.

### The 5 production environment characteristics (Table 1 — C1–C5)

Materialised in [[ml-production-environment-characteristics]]:

- **C1 — Data representation.** ML training data is only a representation of the real world.
- **C2 — Metrics proxy.** Metrics are incomplete proxies for aspects of interest.
- **C3 — Assumptions.** ML applications contain assumptions that may not hold.
- **C4 — Changes.** The production environment changes over time.
- **C5 — Entanglement.** High entanglement with itself and the environment.

### The 17 monitoring practices (Table 3)

Materialised in [[ml-monitoring-quality-cycle]]. Arranged on a 5-step cycle (define / measure / assess / act / control) + 3 cross-sectional. Each practice is explicitly mapped to the C1–C5 characteristics it addresses.

### The 4 drift types (Practice 9)

Materialised in [[ml-drift-types]]:

- **Concept drift** — p(y|x) changes.
- **Data drift** — p(x) changes.
- **Virtual drift** — p(x) changes but p(y|x) holds (benign).
- **Adversarial drift** — malicious data injection.

### Future research directions (Table 4)

Authors flag specific open problems: basic metrics for ML monitoring, drift-type measurement, decision-support systems for ML tradeoffs, communication of adaptations to non-ML stakeholders, monitoring-system architecture, integration with SE processes, required roles and skills for ML monitoring.

## Key data points / statistics

- **23% of companies operating generative ML applications have experienced negative consequences due to inaccuracies** (their citation [10], used to motivate why monitoring matters).
- **15 ML monitoring tools reviewed** (T01–T15) — none implement the full 17-practice surface.
- **5,887 + 399 + 1,473 → 25 final academic articles** after title / abstract / full-text screening + backward search.
- **56 practitioner articles (A01–A56)** retained after exclusion criteria + backward search.
- **10 expert interviews (E01–E10)**; saturation declared after interview 10.
- **385 codes / 31 categories** from the coding analysis.

## Hypothesis touches

- **H1 ([[H1_L0-L7-ladder]]) — neutral.** The substrate-ladder claim is orthogonal to the monitoring question; monitoring practices apply at every ladder position.
- **H2 ([[H2_u-curve-of-value]]) — modestly informative.** The paper provides empirical anchoring for why the middle of the U is harder than it looks: ML applications need a heavy operational stack (the 17 practices) that simple "tooling vendors" — [[ai-development-facilitator]] in Weber's taxonomy — typically under-deliver. But within that middle, monitoring-specific tooling is empirically under-served (15 tools reviewed, none complete) — a possible exception to the squeezed-middle thesis. Also relevant for the top of the U: vendors that bundle monitoring with the application internalise C1–C5 as part of the product, raising switching cost.
- **H3 ([[H3_orthogonal-axes-under-priced]]) — modestly supportive.** Monitoring sophistication is a 2026-era orthogonal axis that Weber's 11-dimension classifier (2021) does not capture — strong candidate addition to [[weber-taxonomy-2026-gaps]] (and may already be partly implicit in the "operational maturity" sub-dimension). Position on this axis is a stronger predictor of which AI startup survives contact with production than position on any ladder.
- **H4 ([[H4_rl-specialization-value-pocket]]) — strongly supportive.** Monitoring is the operational complement to RL specialization. Without C1–C5 mitigation, an RL-fine-tuned proprietary model deployed in a single industrial customer cannot close the [[continual-learning-paradigm]] loop. The paper's 17 practices are a bill of materials for what the H4 vendor has to actually do to keep the model alive past year 1.

## Open questions surfaced

From the paper's Table 4 (future research) and the wiki's reading of it:

- What are the *basic* metrics every ML monitoring stack needs? (paper: open)
- How does one select metrics for ML monitoring in relation to the underlying use case? (paper: open)
- Which drift types exist beyond the four catalogued, and how should each be measured? (paper: open)
- Which components make up a decision-support system for ML tradeoffs (e.g., accuracy vs fairness)? (paper: open)
- How does one bring more knowledge of ML to non-ML employees in an enterprise? (paper: open)
- How does one integrate ML monitoring into an organisation's SE processes? (paper: open)
- What are the relevant roles, responsibilities, and required skills for ML monitoring? (paper: open)
- **(Wiki-internal)** Does a monitoring-tool vendor that implements the full 17-practice surface escape Weber's "AI Development Facilitator" squeezed-middle fate? Could it survive as a stand-alone product or is the only viable form factor embedded inside a vertical AI orchestrator (see [[vertical-ai-orchestration]])?
- **(Wiki-internal)** Is monitoring-stack sophistication the under-the-hood explanation for a non-trivial share of the [[scaling-gap]]? Pilots that work in controlled conditions and silently degrade in production look from the outside like "AI doesn't scale" — but the mechanism may be "the monitoring stack wasn't there."

## Implications for *Where AI Value Lands*

Three load-bearing implications, ranked by how much they should shape the paper:

1. **Monitoring is the operational complement to [[continual-learning-paradigm]] and a precondition for [[H4_rl-specialization-value-pocket]].** Without it, the H4 moat does not compound; the deployed model rots and the customer concludes the technology was never ready. This is the strongest reading of the paper for the project: it supplies the operational vocabulary the H4 vendor's product spec needs.
2. **The [[scaling-gap]] has an operational component the bull-managerial frame under-states.** Bull readings ([[wef-ai-in-action-2025]], [[foundational-enablers]]) attribute the gap to managerial maturity. Bear readings ([[bear-case-synthesis]]) attribute it to capability ceilings. Protschky's reading would add a third: monitoring infrastructure is under-budgeted, so pilots silently degrade. None of the three are mutually exclusive; the third has been the under-named in the wiki so far.
3. **Monitoring sophistication is a candidate orthogonal axis for [[H3_orthogonal-axes-under-priced]] and a candidate addition to [[weber-taxonomy-2026-gaps]].** Two vendors at the same ladder position with the same domain may differ dramatically in survival probability depending on monitoring discipline. This is a 2026-era dimension Weber's 2021 instrument did not need.

## See also

- [[ml-monitoring]] — overview concept page in the tech subfolder.
- [[ml-production-environment-characteristics]] — C1–C5.
- [[ml-monitoring-quality-cycle]] — the 17 practices.
- [[ml-drift-types]] — the four drift types.
- [[eval-real-world-gap]] — upstream framing.
- [[continual-learning-paradigm]] — the moat-deepening loop monitoring enables.
- [[rl-testing-validation]] — pre-deployment counterpart in the same stack.
- [[H4_rl-specialization-value-pocket]] — where Protschky's framework is operationally load-bearing.
- [[vertical-ai-orchestration]] — natural product form factor.
- [[ai-development-facilitator]] — Weber's squeezed middle; monitoring-tool vendors sit here.
- [[scaling-gap]] — operational root cause of pilot failure.
- [[weber-taxonomy-2026-gaps]] — monitoring sophistication as candidate gap dimension.
- [[H3_orthogonal-axes-under-priced]] — monitoring as candidate orthogonal axis.
- [[H2_u-curve-of-value]] — squeezed-middle exception via monitoring tooling under-served.
- [[foundational-enablers]] — implicit enabler not named in the WEF frame.

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*
