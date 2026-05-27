---
title: H4 — RL-Driven Specialization as a New Value Pocket
status: working-hypothesis
confidence: low-to-medium (technically grounded above; business case unvalidated)
tags:
  - hypothesis
  - reinforcement-learning
  - fine-tuning
  - value-capture
  - business-model
last-updated: 2026-05-25
---

# H4 — RL-Driven Specialization as a New Value Pocket

> [!abstract] Hypothesis
> Pre-training has saturated and RL is the load-bearing axis going forward. The entrepreneurial opportunity this opens is not "another generic agent" but **domain-specific RL fine-tuning of a base model, plus the harness around it, sold to a single industrial customer (or as a service across a narrow vertical) as a proprietary operational asset**. The thing being sold is a model that nobody else has — trained on the customer's own process data against the customer's own verifiable reward — and that grows more valuable the longer it runs inside the customer.

> [!warning] Status
> Working hypothesis. Authored in the kickoff conversation of 2026-05-24. The technical premise is grounded in the [[post-scaling-research-pivot]] and [[agentic-scaling-law]] literature, but the **business case is unvalidated on both axes** — willingness to pay and unit economics of the vendor — and RL fine-tuning is costly enough that one wrong assumption sinks the model. Confidence is low-to-medium and asymmetric: higher on "RL will matter more," much lower on "boutique RL-fine-tuning vendors capture meaningful margin."

## The claim, sharpened

The hypothesis rests on four moves, in order.

**First, pre-training scaling has saturated.** This is the [[post-scaling-research-pivot]] claim, articulated from inside the scaling era by Sutskever ([[sutskever-age-of-research]]): natural data is finite, 100× more compute under the current recipe will not produce another five-year leap, and the marginal returns on next-token-prediction pre-training are visibly bending. The architectural-ceiling version of this argument is [[scaling-wall]]; the empirical version is the post-scaling pivot. Either way, capability per dollar of pre-training compute is no longer the axis worth racing on.

**Second, RL is the axis that is still scaling.** Reinforcement learning — particularly [[rl-from-verifiable-rewards]] — is producing the visible capability gains of the last 18 months. Reasoning models, long-horizon coding agents that orchestrate sub-agents over hours, math and formal-logic specialists: these are not products of bigger base models. They are products of post-training on tasks where a reward is *cheap to verify* even when it is *expensive to generate*. The technical pages [[rlhf]], [[rlaif]], [[rl-from-verifiable-rewards]], [[rl-data-preparation]], and [[rl-testing-validation]] document the pipeline; [[agentic-scaling-law]] is the bull-frame reading of what this unlocks.

**Third, this generalises beyond software.** What is true of SWE agents — that a base model plus RL on a verifiable reward plus the right harness produces a system materially better than the base model alone — should hold wherever a domain admits a verifiable reward. The startup / entrepreneurial opportunity is to take a base model, apply domain-specific RL fine-tuning on a customer's proprietary process data, wrap it in the agent harness and context plumbing it needs, and sell the result either to that one customer as a proprietary system or to a narrow vertical as a service. The thing being sold is not a generic LLM wrapper. It is a *proprietary, narrow model trained on the customer's own process data* — closer in spirit to AlphaFold-class domain specialization on protein structure or to the narrow scientific models trained on DNA/RNA sequences than to the consumer fine-tuning patterns visible in image, text-to-3D, or video generation. Those patterns are aesthetic; this one is operational.

**Fourth, the long-term moat is continual.** [[continual-learning-paradigm]] is the mechanism by which the model gets better the longer it runs inside the customer. Each new (state, proposal, outcome) tuple updates the value function. The vendor's defensibility scales not with a single fine-tune but with the *integral* of the customer's process data over time — a moat that begins shallow and deepens. The model that sits inside the customer in year three is not the model that was delivered in year one.

The hypothesis is best read as **a vertical instantiation of the top of [[H2_u-curve-of-value]] for non-software industrials**, with the substrate borrowed from open or licensed base models and the moat located in (i) training-signal design, (ii) operational context, (iii) the harness. It is a [[taker-shaper-maker]] *Maker* posture at vertical scale, not at frontier-lab scale.

## The technical premise (what would need to be true)

The technical premise is several conditional claims stacked on top of each other. The hypothesis only works if *all* of them hold for a given domain.

**A verifiable reward must be constructible.** This is the gating constraint and the one most likely to break a deal. RL from verifiable rewards works precisely because the reward signal is cheap to evaluate even when the trajectory is expensive to generate. For code: did the unit tests pass. For math: does the proof check. For a customer's industrial process: *did the proposed intervention actually move the target KPI in the direction and magnitude predicted, attributable to the intervention rather than to confounders*. Domains where the answer to that question is structurally ambiguous (the customer's process produces multi-causal outcomes with year-long feedback loops and no clean counterfactual) are not candidates for this hypothesis no matter how digital the inputs look. The [[value-functions-as-algorithmic-emotion]] state-space objection bites here: an unboundedly wide trajectory distribution does not become tractable just because the user wants it to.

**The customer's process must produce enough digital traces to recover the RL signal.** Sensor logs, prior proposals, post-intervention outcomes, configuration changes, customer feedback loops — all of it must already exist in a form that can be ingested. Most industrial firms have *some* of this; few have all of it well-structured. The gap between "the data is digital" and "the data is RL-ready" is where most projects die quietly before they begin. [[rl-data-preparation]] is the unglamorous gating step.

**Off-the-shelf base models must be competent enough that fine-tuning is a delta, not a from-scratch project.** This is the cheap version of the premise: the vendor inherits the base model's general reasoning, language, and tool-use, and pays only the marginal cost of pushing it toward the customer's domain. If the base model is too weak — if [[scaling-wall]]-class limitations bind in the customer's domain — RL fine-tuning inherits the limitation and the project becomes a research bet, not a product bet. The honest read is that current base models clear this bar for most digital industrial domains and fail it for anything requiring genuine physical-world modelling ([[world-models-jepa]]).

**Test-time compute is the second axis, not a substitute.** [[agentic-scaling-law]] argues that more inference budget at test time is itself a scaling axis. The hypothesis is *not* that RL fine-tuning replaces test-time compute; it is that the two compound. The fine-tuned model is better *per token of inference budget*, and the harness can spend more tokens on harder cases. The pair is what produces the order-of-magnitude improvements visible in current SWE agents — neither alone gets there.

**Intermediate reward signal is the open research problem.** [[value-functions-as-algorithmic-emotion]] names the bottleneck. Terminal rewards over long industrial trajectories are pathologically sparse: an energy-retrofit proposal's outcome arrives months after the proposal. The tractability of the hypothesis scales with how well intermediate value signal can be constructed — from process-reward models, step-wise verifiers, simulation, supervised cold-start on historicals. This is precisely where the technical risk concentrates.

**Continual learning is the moat-deepening mechanism, not a feature.** Per [[continual-learning-paradigm]], the right architecture for this is one where the model updates as outcomes come back. The vendor's defensibility *is* the continual loop. If the vendor cannot stand up a continual-learning architecture against the customer's data, the moat does not compound and the deliverable degrades to a one-shot fine-tune that the next vendor can replicate from the same base model.

## The business premise (what would need to be true)

The author flagged this as the under-validated side, and it is. The technical premise can be checked against the literature. The business premise has to survive contact with industrial procurement, and that test has not been run.

**Willingness to pay.** Why would a non-tech company pay more for a fine-tuned model than for a clever agent on a base model + retrieval? The argument is that a *proprietary model trained on their own process data* is a proprietary asset — on-balance-sheet IP, not a renewable OpEx subscription, not switchable in the way a SaaS contract is switchable. The contrast is with the "thin wrapper" failure mode catalogued in [[middle-layer-defensibility]]: a wrapper has no IP, no proprietary substrate, and survives only as long as the underlying model and the customer's habit. A fine-tuned model has weights the customer can (in some commercial arrangements) license, host, or co-own. The willingness-to-pay argument is structural: the customer is buying *ownership*, not access. Whether industrial procurement actually parses this distinction — or whether it commodity-prices the result regardless — is the empirical question.

**Sales surface.** This is not a SaaS subscription. Contract length runs in years, sales cycles run in quarters, the signers are operations and engineering leadership rather than IT. The closest existing analogues are enterprise software pilots that convert into multi-year industrial services contracts — Siemens MindSphere deployments, ER&I orchestrator engagements documented in [[deloitte-ai-dossier-eri]], industrial-AI co-development arrangements with the major systems integrators. The implication is that the vendor's go-to-market is closer to a defence contractor's than to a SaaS startup's: long pilots, reference customers, certification overheads, and revenue lumpiness that frightens conventional venture economics.

**Defensibility.** This maps cleanly onto top-of-U logic in [[H2_u-curve-of-value]]. The customer's data, the trained value function, and the orchestration harness compose into a [[distribution-moat]] *inside one customer* (or one tight vertical). It is not a horizontal moat — it does not transfer to the next customer without re-training. The vendor's defensibility against displacement by the next vendor is the operational context, the incident history, and the continual-learning loop already accumulated. This is the same shape as [[vertical-ai-orchestration]] in industrials, with the model layer pulled into the moat rather than treated as an OEM input.

**Where the surplus is created vs captured.** The distinction matters and is easy to miss. *Value creation* sits on the customer side — the process automation savings, the labor reallocation, the throughput improvement, the avoided incident. *Value capture* is the price the vendor extracts from that surplus. The vendor's pricing power is bounded by (i) the customer's ability to estimate the surplus, (ii) the customer's ability to build the same thing in-house, and (iii) the rate at which frontier labs erode the differentiation. See [[value-capture]] for the structural distinction. The bear reading is that most of the surplus accrues to the customer and the vendor captures a thin services margin; the bull reading is that the proprietary-asset framing supports per-customer contract values that scale with savings.

**Closest archetypal precedents.** Vertical AI orchestrators in industrials are the structural precedent ([[vertical-ai-orchestration]], [[deloitte-ai-dossier-eri]]), with the difference that the hypothesised vendor pulls the model layer into its scope rather than treating foundation models as a generic input. On the SME side, [[sme-champion-vertical-ai]] is the small-scale analogue. AlphaFold-style domain specialization is the technical analogue but not the commercial one — DeepMind did not sell AlphaFold as a per-customer fine-tune; it released a tool and captured strategic, not commercial, value. The hypothesis is closer to "AlphaFold built as a service for a single industrial customer's process" than to "AlphaFold-as-a-platform."

**Seller-side archetype lineage (Weber et al. 2021).** Within [[ai-startup-business-archetypes-weber]] the hypothesis sits inside the [[ai-deep-tech-researcher]] pattern, with one important 2026 update relative to the 2021 paper: in Weber's sample, Deep Tech Researchers typically built their own base technology (Cerenion, Syrius Robotics). In the H4 sub-pattern, the vendor *does not train its own base model* — it RL-fine-tunes someone else's. This makes the capital intensity lower and the time-to-first-contract shorter than the 2021 archetype suggests, while preserving the Deep Tech Researcher pattern's defensibility profile (research-led, niche, custom, externally-funded early).

**Connection to [[taker-shaper-maker]].** This hypothesis sits squarely in the *Maker* corner — not at frontier-lab scale, but at vertical scale. The customer pays the vendor to *make* a model that did not exist before, against their own data, with their own reward function. The vendor is not a *Taker* (would buy and resell the base) nor a pure *Shaper* (would only customize the prompt and the retrieval layer). The Maker posture is the source of the defensibility argument and also the source of the cost argument.

**Cost.** Frontier RL fine-tuning is currently expensive enough to swallow most of the early-stage capital of a startup. The unit-economics question is whether the customer contract value can cover (training cost + harness build + maintenance + continual-learning compute) and still yield gross margin sufficient to scale beyond services-revenue. Most likely path, by analogy with the industrial-services market: services revenue funds the IP build for the first 2–3 customers, the value function and harness generalise across the third and fourth customer at substantially lower marginal cost, and the firm productizes from there. This is the same shape every industrial-AI services firm has tried to walk; few have made it to product.

## Concrete worked example: the industrial-implant proposal model

The author's example, kept faithful. A company runs an internal process — entirely digital — that takes energy data and the initial state of a physical implant or plant, layers in objectives (cost reduction, throughput, emissions reduction), and produces a proposal of which interventions to perform to make the implant work better. Which retrofits, which parameter changes, which equipment swaps, in which order, at what cost, with what expected payback. Today this is done by internal human know-how — domain engineers with twenty years of plant-specific experience, doing a process that is partially codified in spreadsheets and partially residing in their heads.

**The data that exists.** Sensor logs from the implant (energy consumption, throughput, fault events, sensor anomalies). Historical proposals — what was proposed, what was implemented, what was deferred, what was rejected. Post-intervention outcomes — did the KPI move, by how much, on what timeline. Engineering review notes, customer correspondence, parts catalogues, vendor specifications. The data is not clean and it is not RL-ready — but it exists in the customer's systems and the customer's heads, and a non-trivial fraction of it is digital.

**The verifiable reward.** "Did the proposed intervention actually improve KPI X by Y after deployment, attributable to the intervention?" Verifiable in principle: KPIs are measured, deployment dates are recorded, outcomes are tracked. Verifiable in practice with caveats: attribution is partial (external factors move KPIs too), the measurement window is long (months), and the counterfactual is not directly observable. The reward is constructible but noisy.

**The RL signal density problem.** This is the load-bearing risk. Interventions have feedback loops measured in months, not minutes. A single trajectory — from initial state to proposal to deployment to outcome — yields one labeled tuple after six months. A model that needs ten thousand such tuples to learn cannot wait for them to arrive in real time. The solutions are: (i) collect historical (state, proposal, outcome) tuples as a static dataset, (ii) cold-start with supervised fine-tuning on the historicals to give the model competent first-draft behaviour, (iii) construct simulation environments where intervention outcomes can be predicted from physical models or learned dynamics, (iv) run offline RL against that simulator with reward modelling that compares simulated outcomes to historical analogues, (v) deploy as harness alongside human reviewers who score proposals on a richer intermediate rubric, generating denser feedback than terminal outcomes alone. Whether this stack converges in any specific industrial domain is an empirical question per domain.

**The build path.** Collect historical tuples → cold-start with supervised fine-tuning → construct intermediate reward signal (process reward model, expert rubric, simulator) → run RL with offline data → deploy as harness alongside human reviewers, capturing each new proposal and its eventual outcome as training data → continual-learning loop on the deployed model. Each step has well-understood research methods and ill-understood failure modes against industrial data.

**The growth path.** As the model proposes more interventions and outcomes come back, the value function improves and the intermediate reward signal sharpens. [[continual-learning-paradigm]] applies: the vendor's moat at year three is the integral of all proposals and outcomes the model has seen inside the customer. A second-mover trying to displace the vendor in year three faces not just a model that is better than the base, but a model that is better than the base *trained on data the second-mover does not have access to*.

**Where the deal could break.** Five places, in rough order of likelihood. *Outcome attribution* — the customer cannot cleanly distinguish intervention-driven KPI movement from external factors, so the reward signal stays too noisy to converge. *Data ownership* — the customer refuses to allow the vendor to retain training rights on their proprietary process data, which collapses the continual-learning moat. *Exclusivity* — the customer demands exclusivity in their geography or sub-vertical, which prevents the vendor from amortising IP across customers. *Internal competition* — the customer's internal engineering team perceives the vendor as a threat to their domain authority and slow-walks the project. *Frontier displacement* — a frontier lab ships an enterprise-fine-tuning API that closes 70% of the gap at 10% of the cost before the vendor's first contract renews.

## Why this might be wrong

The bear case for this hypothesis is strong enough that the symmetric treatment matters more than the bull frame.

- **Base models plus clever orchestration may close enough of the gap that fine-tuning isn't worth the cost.** [[agentic-scaling-law]] argues test-time compute is itself a scaling axis. [[context-control]] argues sophisticated harness design — observability, time-travel debugging, graph-based orchestration — is where defensible middle-layer infrastructure lives. The composite reading is that the harness, not the weights, is where the value lives. If true, the hypothesis collapses into "vertical AI orchestration" without the model layer, and the vendor's RL fine-tuning expense becomes margin destruction rather than moat construction.

- **Verifiable rewards may not exist for messy industrial domains.** Most real-world industrial processes do not produce crisp end-state KPIs that close the credit-assignment loop on the relevant timescale. The [[value-functions-as-algorithmic-emotion]] state-space objection applies: an unboundedly wide trajectory distribution combined with sparse, noisy terminal rewards may simply not converge into a useful policy, no matter how much capital is thrown at it. This is the technical-side equivalent of the business-side defensibility question — and the most likely place the hypothesis fails on its own merits.

- **Customers may refuse to share proprietary process data with a vendor.** This is particularly acute in European industrials and in family-owned industrial firms, where know-how is treated as multi-generational IP and is, in some cases, structurally inseparable from family identity (the Italian SME tradition is the sharpest version). Even where the customer is in principle willing, data exclusivity contracts will frequently prohibit the vendor from training on the data in a way that improves the model for other customers — which collapses the cross-customer amortisation that makes the unit economics work.

- **The vendor never reaches escape velocity from being a services business.** Every customer is a custom build. The value function does not generalise across customers because the customers' processes do not generalise across customers. Gross margin stays at consultancy levels (30–45% rather than software levels of 70–85%), and the firm cannot scale beyond the headcount of senior ML engineers it can hire. This is the failure mode of nearly every industrial-AI services firm that has ever tried to graduate into product.

- **Frontier labs absorb the capability.** Anthropic, OpenAI, Google ship enterprise-fine-tuning products (already partially true today — Anthropic and OpenAI both offer fine-tuning surfaces, OpenAI's RFT product is an early version of exactly this idea) that price the boutique vendor out of the market. The vendor's moat against the frontier lab is operational context and harness, not the fine-tuning step itself — but the frontier lab can sell the fine-tuning step at marginal cost while the vendor has to fund the entire training stack.

- **The [[scaling-wall]] argument generalises into the customer's domain.** If next-token-prediction base models lack the world model needed to reason about physical implants — [[world-models-jepa]] is the strongest version of this argument — then RL on top inherits the limitation. The fine-tuned model produces plausible-sounding proposals that fail in the field, and the customer concludes (correctly, in this branch) that the technology was not ready.

- **Long feedback loops make RL signal pathologically sparse.** Industrial outcomes arrive on months-to-years timescales. The offline-RL + supervised cold-start + simulator path may simply not converge in any specific industrial domain that hasn't been instrumented for it. Even if the technical stack is sound, the data isn't.

## What would retire this hypothesis

The hypothesis should be retired — not merely revised — if any of the following are observed.

- **18 months on (≈ end of 2027), zero non-toy customer-funded RL-fine-tuned proprietary models survive a renewal cycle in non-tech industrials.** The hypothesis predicts at least a handful of multi-year industrial contracts with renewals; the absence of those is the strongest negative signal.
- **Frontier-lab fine-tuning APIs collapse the cost differential to ~zero.** If OpenAI, Anthropic, and Google price enterprise RL fine-tuning at marginal compute cost — and ship it with a harness — the boutique vendor's value proposition disappears.
- **A credible meta-study shows base-model + retrieval + tools matches RL-fine-tuned model performance on >80% of worked industrial benchmarks at <10% the cost.** This is the "the harness is the moat, not the weights" version of the bear case made empirically.
- **The long-feedback-loop sparsity problem proves intractable across 3+ published industrial case studies** using synthetic data, offline RL, and intermediate-reward modelling. If the technical stack does not converge in well-funded published attempts, it will not converge for a boutique startup either.
- **Customer interviews consistently report data exclusivity and IP-ownership demands that prohibit cross-customer amortisation.** If the contractual terrain forecloses the unit economics, the hypothesis cannot scale even where the technology works.

## Open research questions

- At what customer contract size (€/year) does dedicated RL fine-tuning break even against an equivalently good base-model + harness? The crossover point determines the addressable market.
- Which industrial verticals have the cleanest verifiable-reward structure? Energy retrofitting (KPI = post-retrofit energy savings vs prediction), predictive maintenance (KPI = avoided downtime), generative site design (KPI = built-spec match against specification), grid optimization (KPI = stability + cost dispatch) are the natural first candidates. See [[predictive-maintenance]], [[generative-site-design]], [[grid-optimization]].
- Is the right vendor archetype "services firm graduating into product" or "product firm starting from custom"? Are there extant examples of either succeeding past the seed stage in the post-2024 RL era specifically? The historical industrial-AI services market has very few graduations to point to.
- How does the [[oecd-sme-adopter-taxonomy]] map onto this hypothesis? Champions are the natural customer; do Optimisers ever buy custom RL models? The hypothesis may live entirely inside the Champion-and-above population.
- Where on the [[H1_L0-L7-ladder]] does this hypothesis sit? Working answer: L3–L5 substrate (the vendor sits at L4 — dedicated sandbox + harness — for the customer who otherwise sits at L1–L2), Phase 3+ maturity on the buyer side, Maker posture in the [[taker-shaper-maker]] decomposition. Confirm by case-study.
- Open-source vs closed-source RL fine-tuning APIs ([[rl-apis]], [[rl-open-vs-closed-source]]): does the boutique vendor's economics tilt toward open-weight bases (lower marginal cost per fine-tune, higher engineering burden) or toward closed APIs (higher marginal cost, lower burden, captured by the API provider)? The question is whether the vendor competes with the lab on which compute the customer's data sits on.
- What is the right reward-modelling architecture for the domains where outcomes are months out? Process reward models, expert-rubric annotation, simulation-based reward, or some composite? [[rl-testing-validation]] is the testbed.

## Related

- [[H1_L0-L7-ladder]] — substrate map; this hypothesis lives at L3–L5 for the buyer with the vendor at L4–L5 on their behalf.
- [[H2_u-curve-of-value]] — economic frame; this hypothesis is a top-of-U claim for non-software industrials.
- [[H3_orthogonal-axes-under-priced]] — what the prior hypotheses leave out; RL specialization may be one of the missing axes.
- [[scaling-wall]] — the architectural ceiling RL is asked to route around.
- [[post-scaling-research-pivot]] — Sutskever's reframing of the broader paradigm shift this hypothesis sits inside.
- [[agentic-scaling-law]] — the test-time-compute axis that compounds with RL fine-tuning.
- [[value-functions-as-algorithmic-emotion]] — the open research problem (intermediate reward signal) on which technical tractability hinges.
- [[continual-learning-paradigm]] — the moat-deepening mechanism.
- [[eval-real-world-gap]] — the failure mode the hypothesis must avoid (good benchmarks, bad field performance).
- [[world-models-jepa]] — the paradigm-reset risk for any current-generation model trained on physical processes.
- [[middle-layer-defensibility]] — the failure mode (thin wrapper) the hypothesis explicitly distinguishes itself from.
- [[distribution-moat]] — the structural mechanism that defends the top of the U inside one customer.
- [[context-control]] — the bear-case sharpening: the harness, not the weights, may be where the value lives.
- [[vertical-ai-orchestration]] — the closest existing concept; this hypothesis is vertical AI orchestration with the model layer pulled into the moat.
- [[value-capture]] — surplus creation vs surplus capture; the pricing-power question.
- [[taker-shaper-maker]] — strategic-positioning axis; this hypothesis is a *Maker* posture at vertical scale.
- [[sme-champion-vertical-ai]] — the SME-scale instantiation of the pattern.
- [[oecd-sme-adopter-taxonomy]] — the buyer-side decomposition; Champion firms are the natural customer.
- [[deloitte-ai-dossier-eri]] — the closest non-software vertical instantiation in the wiki.
- [[predictive-maintenance]] — candidate vertical with relatively clean verifiable reward.
- [[generative-site-design]] — candidate vertical; spec-match as reward.
- [[grid-optimization]] — candidate vertical; stability + cost dispatch as reward.
- [[karpathy-software-3]] — the bull-frame source for software-3 / agentic-scaling logic that this hypothesis extrapolates from software into industrials.
- [[sutskever-age-of-research]] — the primary source for the post-scaling pivot framing.
- [[rlhf]] — the foundational RL-from-human-feedback technique.
- [[rlaif]] — the AI-feedback variant; relevant for domains where human annotation does not scale.
- [[rl-from-verifiable-rewards]] — the technique the hypothesis is built on.
- [[rl-data-preparation]] — the unglamorous gating step.
- [[rl-testing-validation]] — the validation pipeline.
- [[rl-open-vs-closed-source]] — the strategic question on which the vendor economics tilt.
- [[rl-apis]] — the commercial surface the vendor competes against.
- [[ml-monitoring]] — the operational complement to RL specialization; the C1–C5 / 17-practice surface is a bill of materials for what the H4 vendor's deliverable has to include past the model itself.
- [[ml-production-environment-characteristics]] — every C-characteristic is sharper for a narrow-domain industrial deployment; C1 (training-data narrowness), C4 (the customer's process *is* the changing thing the model adapts to), and C5 (harness is part of the moat) are especially binding.
- [[ml-monitoring-quality-cycle]] — Practice 16 (iterative continual learning from production) is what closes the H4 moat-deepening loop; Practices 8–11 are what catch silent rot.
- [[ml-drift-types]] — drift on the customer's specific process is the binding operational risk; the vendor's defensibility depends on detecting drift before the customer's process engineers do.
- [[protschky-ml-monitoring-2025]] — empirical source for the monitoring stack the H4 vendor has to actually build.
- [[specialist-subagent-for-orchestrators]] — buyer-side composition framing of this hypothesis: the H4 artifact sold as a callable MCP node inside someone else's agent orchestrator; reframes "sold to a single industrial customer" into "rented by N agent builders for one node in their graph."

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*

**Paper planning**
- [[05_open-questions]]

**Hypotheses**
- [[H1_L0-L7-ladder]]
- [[H2_u-curve-of-value]]
- [[H5_ai-as-operational-not-product]]

**Concepts**
- [[agentic-scaling-law]]
- [[ai-deep-tech-researcher]]
- [[ai-development-facilitator]]
- [[ai-startup-business-archetypes-weber]]
- [[continual-learning-paradigm]]
- [[ml-drift-types]]
- [[ml-production-environment-characteristics]]
- [[post-scaling-research-pivot]]
- [[scaling-wall]]
- [[value-functions-as-algorithmic-emotion]]
- [[weber-taxonomy-2026-gaps]]

**Sources**
- [[protschky-ml-monitoring-2025]]
- [[weber-ai-startup-business-models]]
- [[westerveld-business-model-portfolio-2023]]

**Tech**
- [[tech/README]]
- [[ml-monitoring]]
- [[rl-apis]]
- [[rl-data-preparation]]
- [[rl-from-verifiable-rewards]]
- [[rl-open-vs-closed-source]]
- [[rl-testing-validation]]
- [[rlaif]]
- [[rlhf]]
