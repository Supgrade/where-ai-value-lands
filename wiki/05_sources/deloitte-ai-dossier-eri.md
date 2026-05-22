---
title: "Source: Deloitte AI Dossier — ER&I Use Cases"
status: ingested
tags:
  - source
  - deloitte
  - vertical
  - eri
  - industrial
  - agentic
  - bull-frame
last-updated: 2026-05-22
---

# Deloitte AI Dossier — AI Use Cases in Energy, Resources & Industrials

> [!info] Citation
> Synthesis of the *Deloitte AI Dossier*, ER&I sector chapter, integrated with WEF *AI in Action* (2025) case studies and the Karpathy/Huang Software-3.0 paradigm. Raw file: `raw/AI use cases in Energy, Resources, and Industrials (ER&I) sectors from  Deloitte AI Dossier.md`.
>
> **Stub-via-synthesis.** This is an LLM-authored "PhD-level analysis" of the Deloitte dossier — not the dossier itself. The Deloitte primary document and Huang's GTC keynotes still need direct ingestion. See [[karpathy-software-3]] for a parallel synthesis problem.

## Central claim

ER&I (Energy, Resources & Industrials) is transitioning from **reactive, labor-intensive operational models** to **proactive, autonomous, agentic ecosystems**. In asset-heavy industries — where precision, safety, and margin pressures dominate — AI is no longer an analytical tool but an **active orchestrating agent** managing physical assets, field personnel, supply chains, and power grids.

This is the most concrete vertical articulation in the wiki of the [[agentic-revolution]] — the transition from *analytical* AI (predicts a breakdown) to *agentic* AI (predicts the breakdown, orders the part, reroutes the supply chain, schedules a drone inspection, escalates to a human only on exception).

## Stance

Bull-frame consultancy synthesis. Deloitte has direct commercial interest in framing the transition as inevitable and orderable — their advisory practice sells the "Trustworthy AI™" governance overlay that they argue is the gating condition. The source is internally self-aware about limits (OOD failures, dark-data scarcity, cyber-attack surface), which keeps it more credible than pure marketing copy, but the *framing* is closer to [[wef-ai-in-action-2025]] than to the bear cluster.

The source does not engage with [[bear-case-synthesis]], [[circular-ai-economy]], or [[task-based-framework]]. It treats AI deployment in industrials as a **management + governance + data-readiness problem** — not a question of whether the underlying surplus or substrate economics work.

## The 12 ER&I use cases

Grouped into four operational domains. Each is asserted as live or near-term in Deloitte's client base; WEF case studies are cited as corroboration. Each use case has a dedicated pattern page in `06_ideas/` browsable independently of this source.

### A. Asset lifecycle and field operations
1. [[predictive-maintenance]] — multimodal sensor ingestion, multi-agent RL diagnoses root cause + generates work orders + schedules around production cycles. *WEF corroboration:* SBB (60% inspection-time reduction via computer vision on pantographs); Siemens (energy + waste reduction).
2. [[autonomous-drone-inspection]] — "drone-in-a-box" BVLOS missions for power lines, pipelines, transmission towers; thermal + visual + LiDAR; orchestration agent schedules fleets without a human pilot. *WEF:* >50% cycle-time reduction in electrical distribution inspections.
3. [[drone-footage-smart-summaries]] — NLP + computer vision generate queryable summaries from drone footage (e.g. Optical Gas Imaging for VOC leaks). User asks plain-English questions.
4. [[autonomous-field-operations]] — multi-agent systems mimic expert field units: one diagnoses, one reschedules technicians, one ensures regulatory compliance. *WEF:* Aker BP's "Yggdrasil" project — periodically unmanned offshore platforms with onshore human oversight.

### B. Exploration, R&D, mineral processing
5. [[hydrocarbon-reservoir-exploration]] — AI denoises poor seismic data, generates synthetic samples, integrates well logs + core + production data to simulate reservoir dynamics. Reduces dry-drilling financial risk. See [[synthetic-data-generation]].
6. [[minerals-processing-optimization]] — AI maps and categorizes ores, generates synthetic samples to model properties without physical testing, optimizes grinding/flotation. Yields up; hazardous chemicals down.
7. [[ai-materials-science]] — AI virtually screens chemical compositions in materials science (e.g. High-Entropy Alloy engineering), removes redundant physical R&D. *WEF:* Merck's sequential-learning AI for semiconductor materials saved hundreds of thousands of euros per testing campaign.

### C. Grid, supply chain, commercial
8. [[grid-optimization]] — AI digitizes legacy maps, simulates trading under regulatory regimes, designs optimal grid-expansion configurations, runs genAI chatbots for consumer demand-response incentives. Direct ER&I anchor for the WEF "Energy Paradox": AI consumes power, but AI-enabled smart grids are the primary mitigation tool.
9. [[supply-chain-digital-twin]] — digital twin of operations; "what-if" scenarios; tier-n supplier risk; natural-language query over global logistics. *WEF:* BMW's multi-agent genAI platform reports 30–40% productivity gains.
10. [[intelligent-commercial-operations]] — demand-forecasting agent + pricing agent + bid-preparation agent draft proposals; post-sale agents monitor contracts for margin erosion.
11. [[generative-site-design]] — generative design of industrial site blueprints (solar orientation, traffic flow, accessibility), auto-annotated with specs and materials.

### D. Human capital and safety
12. [[vr-ohs-training]] — AI + VR generates customized hazard simulations based on real incident reports and local compliance, safely exposing workers to dangerous scenarios.

## Frameworks contributed to the wiki

- **Agentic revolution (analytical → agentic).** The single load-bearing concept. See [[agentic-revolution]].
- **Iron Man Suit imperative in physical/industrial contexts.** Deloitte explicitly warns against full autonomy in ER&I: "AI models simulating reservoir drilling or field safety must have escalation paths… for manual review." This is the strongest vertical-domain corroboration of [[autonomy-slider]] outside software.
- **Trustworthy AI™ governance model.** Deloitte's branded framework gating ER&I deployment. Not theoretically novel — overlaps heavily with the [[foundational-enablers]] in [[wef-ai-in-action-2025]] — but it operationalizes the warnings against unsupervised physical-asset AI.
- **Vertical multi-agent orchestration as moat.** The orchestrator-of-orchestrators (fault diagnosis + technician scheduling + compliance check + supply-chain rerouting) is the unit of value capture, not the underlying LLM. See [[vertical-ai-orchestration]].
- **Synthetic data generation as the dark-data workaround.** A concrete methodology asserted as essential for asset-heavy industries where natural data on rare catastrophic events (pipeline fractures, cyber-attacks on grids) is scarce by definition. See [[synthetic-data-generation]].
- **AI Factory (Huang).** The source explicitly invokes Huang's framing: industrial sensor data → manufactured intelligence at the edge. See [[ai-factory-huang]].

## Methodological limitations Deloitte itself flags

Worth preserving because they are unusually candid for a consultancy frame:

- **Out-of-distribution generalization failure.** In mineral processing and hydrocarbon exploration, models are "heavily bounded by their training data" and struggle on "novel ores" or unfamiliar ecological scenarios — producing "suboptimal processing recommendations" or costly false positives. Direct vertical-application-layer manifestation of [[scaling-wall]].
- **Dark-data scarcity.** ER&I sectors lack clean structured data; rare catastrophic events (pipeline fractures) have almost no natural training signal. The proposed fix is [[synthetic-data-generation]] — useful but introduces its own physics-fidelity risk.
- **Adversarial cyber surface.** Because the AI now controls drones, grids, and pipelines, signal spoofing and intrusion detection become safety problems, not IT problems. Adversarial robustness is now a load-bearing requirement, not an optional hardening pass.
- **Ethics and systemic bias.** Vendor bias in commercial ops + sustainability blind-spots in materials design (efficiency-optimizing AI ignores long-horizon environmental cost) require explicit multi-objective alignment by human developers.

## Contributions and tensions

**Contributes to the wiki:**
- The first ingested source with a **deep vertical-domain decomposition**. Where [[karpathy-software-3]] and [[wef-ai-in-action-2025]] argue at the paradigm level, Deloitte names 12 concrete operational anchors per which AI value would or would not materialize.
- A **non-software** instantiation of [[middle-layer-defensibility]]: the workflow-embedded platform survives, the thin wrapper dies — in physical industrials as in SaaS.
- A **non-US-stack** lens implicitly: ER&I cases are global (Aker BP / Norway, BMW / Germany, SBB / Switzerland, Merck / Germany, Siemens / Germany). The vertical-industrial value-capture story is geographically distributed in a way the software-stack story is not. This sits adjacent to [[divergent-value-stack-optima]] but pulls a different lever (sector, not geopolitics).

**Tensions surfaced:**
- **Where does value land in industrials?** Deloitte's implicit answer: at the **orchestration layer that coordinates the physical operation** plus the **proprietary operational data + physical assets that the AI consumes and acts on**. This is a vertical-domain U-curve — top is the multi-agent operational platform; bottom is the sensors, assets, and data. Generic LLMs are in the squeezed middle. See [[H2_u-curve-of-value]] for the update.
- **OOD failure is bear-compatible.** Deloitte's candid admission that models fail on "novel ores" or unfamiliar geology is consistent with [[scaling-wall]] / [[marcus-world-models-failure]] in a way the source itself does not draw out. It is a self-aware bull frame that lands closer to the bear case than its own conclusion does.
- **Magnitude is unquantified.** Unlike [[wef-ai-in-action-2025]] ($7.6–17.9T projection) or [[task-based-framework]] (<0.71% TFP cap), Deloitte does not commit to a sector-wide economic-impact number. It enumerates use cases without aggregating their surplus. This is harder to test but also harder to falsify.
- **Agentic full-stack assumes the surplus exists.** "Predicts a breakdown, orders the part, reroutes the supply chain, schedules a drone" is the long-tail-of-tasks bull-frame articulation — directly the opposite of [[task-based-framework]]'s static-task framing. If Acemoglu is right that the automatable task-set is small, the agentic-revolution narrative is overclaiming. If Deloitte is right that the task-set expands as agents take over orchestration, the cap is wrong.

## Quotable

> "The competitive moat in ER&I will no longer be determined solely by physical assets (oil reserves or factories), but by the maturity of an organization's digital core, its data ecosystems, and its ability to securely manage hybrid human-AI workforces."

The single load-bearing strategic claim. Notable for *not* placing the moat at the AI model — placing it at orchestration + data + workforce coordination. Directly compatible with [[middle-layer-defensibility]] and [[distribution-moat]] when "distribution" is reread as "ownership of the operational user-and-asset relationship."

> "AI models simulating reservoir drilling or field safety must have escalation paths… for manual review."

The Iron Man Suit ([[autonomy-slider]]) restated in physical-infrastructure terms. The asymmetric reliability problem — "a 99% autonomous agent is not 99% of a 100% autonomous one — it's catastrophic" — is precisely why full autonomy is forbidden in ER&I.

## Methodology

This is a synthesized analysis, not original Deloitte text. The synthesis layers three documents: the Deloitte AI Dossier (primary, not directly verified), [[wef-ai-in-action-2025]] (corroboration on specific case studies), and [[karpathy-software-3]] (theoretical paradigm anchors).

No primary data collection. Case studies are second-hand. Numerical claims (60% inspection-time reduction at SBB, 30–40% productivity gain at BMW, >50% cycle-time reduction in electrical inspections) trace through the WEF document and would need verification against company reporting.

## Data surfaced by this source

- [[eri-use-case-deltas]] — SBB 60% / Aker BP / BMW 30–40% / Merck €100k / drone >50% table.

## Related

- [[agentic-revolution]] — the load-bearing concept this source introduces.
- [[vertical-ai-orchestration]] — the moat structure for industrial-domain AI.
- [[synthetic-data-generation]] — the dark-data workaround.
- [[ai-factory-huang]] — Huang's framing that Deloitte adopts.
- [[autonomy-slider]] — vertical-specific corroboration of the Iron Man Suit imperative.
- [[H1_L0-L7-ladder]] — the 12 use cases sit at L3–L5 (agent decides → fleet of agents) in industrial verticals.
- [[H2_u-curve-of-value]] — vertical-domain U-curve evidence: top is orchestration, bottom is data + assets.
- [[middle-layer-defensibility]] — non-software instantiation of the workflow-embedded-platform thesis.
- [[distribution-moat]] — reread as "ownership of the operational user-and-asset relationship" in industrials.
- [[scaling-wall]] — OOD generalization failure is the application-layer manifestation.
- [[karpathy-software-3]] — paradigm parent; Deloitte invokes Karpathy/Huang explicitly.
- [[wef-ai-in-action-2025]] — corroborating WEF case studies (SBB, Siemens, BMW, Merck, Aker BP).
- [[foundational-enablers]] — overlap with Deloitte's Trustworthy AI™ governance overlay.
- [[bear-case-synthesis]] — the cluster the Deloitte source does not engage with.
- [[task-based-framework]] — the unquantified-magnitude question this source sidesteps.
- [[oecd-sme-ai-adoption-2025]] — complementary OECD G7 source on SME-side AI diffusion.
- [[sectoral-ai-diffusion-pattern]] — sectoral lag in ER&I-adjacent sectors (construction, manufacturing, transportation) is one of the OECD source's main findings.
- [[oecd-sectoral-ai-adoption-2024]] — sectoral adoption data that contextualises Deloitte's ER&I-specific narrative.
