---
title: ML Monitoring
status: reference
tags:
  - tech
  - monitoring
  - mlops
  - production
  - protschky
last-updated: 2026-05-25
---

# ML Monitoring

> [!abstract] One-line
> The continuous performance measurement of a deployed ML application — across data, model, infrastructure, and business layers — so that drift, data-quality issues, and silent failures are detected and acted on before they cost the customer money.

ML monitoring is the operational discipline that sits *after* deployment. It is the production-environment counterpart to [[rl-testing-validation]] (which runs pre-deployment) and the operational layer the MLOps stack notoriously *does not* cover well. The canonical 2025 framing — five production-environment characteristics + seventeen monitoring practices arranged on a quality-management cycle — comes from [[protschky-ml-monitoring-2025]].

## Why ML monitoring is not just software monitoring

DevOps-era monitoring measures CPU, memory, request latency, error rates. ML applications inherit all of that and add five characteristics that conventional monitoring does not handle ([[ml-production-environment-characteristics]]):

- **C1 — Data representation.** Training data is only ever a slice of reality.
- **C2 — Metrics as proxy.** Accuracy, F1, MAPE — none of them measure the thing you actually care about; they measure a stand-in.
- **C3 — Assumptions.** Embedded assumptions about the world break silently.
- **C4 — Changes.** The world moves. The model does not, unless someone moves it.
- **C5 — Entanglement.** Data, features, model, downstream services, business metrics — all coupled, all moving, all hard to attribute.

These five characteristics make ML monitoring an open practice problem rather than a tooling-checkbox problem. [[protschky-ml-monitoring-2025]] reviewed 15 ML monitoring tools and found that none of them implement the full practice surface.

## The MLOps gap

MLOps as documented in the literature focuses on workflow automation — pipelines, retraining triggers, model registries, CI/CD for models. The Protschky synthesis is explicit: MLOps "lacks in-depth guidance for monitoring issues specific to ML models." Monitoring is the under-served stratum of MLOps — present in the diagrams, thin in the practice.

This is a wedge. The 2021 Weber taxonomy classifies tooling vendors as [[ai-development-facilitator]] — the squeezed middle of [[H2_u-curve-of-value]]. But the practice gap above suggests a niche that survives the squeeze: monitoring tooling that operationalises the C1–C5 specifics, sold to enterprise ML teams who otherwise inherit the failure cost themselves. See [[ml-monitoring-quality-cycle]] for the 17-practice surface a monitoring tool would need to cover.

## What ML monitoring actually does

Four layers of measurement, all required, none sufficient on its own:

- **Input/data layer** — statistical moments, missing-value rates, feature drift, schema breaks. Detects upstream pipeline issues and distribution shift in the inputs.
- **Model/output layer** — prediction distributions, confidence calibration, latency, behavioural drift. Detects when the model's *behaviour* changes even when inputs don't.
- **Performance layer** — accuracy, F1, business metric, A/B against ground truth. Detects when the model is wrong in ways the input/output layers miss. Requires ground truth, which is often delayed or unavailable.
- **Business layer** — revenue impact, customer satisfaction, downstream KPI. The only layer that measures whether the model is *creating value*. Often months delayed; often the only one decision-makers care about.

The non-trivial design problem: build alerting that fires only when *all four layers* corroborate a real issue, not when one statistical test flickers. See [[ml-monitoring-quality-cycle]] for the practice arrangement and [[ml-drift-types]] for the drift-detection-specific sub-surface.

## The two-layer abstraction

Protschky et al. frame ML monitoring through a **real-world layer** ↔ **representation layer** split. The representation layer is everything that exists inside the ML system: training data, features, model weights, output distributions, metrics. The real-world layer is the phenomenon those things are *supposed to be about*: actual customer behaviour, actual machine wear, actual fraud occurrence.

The monitoring entity sits between the two and tries to detect when representation and reality have drifted apart. The two layers communicate through the eight measurement areas in Figure 1 of [[protschky-ml-monitoring-2025]]: agents (1), input data (2), preprocessing/storing (3), metadata (4), algorithm (5), output (6), task (7), business value (8), with infrastructure as the substrate.

This two-layer framing is the operational version of [[eval-real-world-gap]]: the eval lives in the representation layer; the real-world layer is what bites.

## Where this fits in *Where AI Value Lands*

The monitoring discipline is load-bearing for several wiki claims:

- **[[H4_rl-specialization-value-pocket]].** An RL-fine-tuned proprietary model deployed inside a single industrial customer is *only* defensible if the vendor can detect when the model's behaviour drifts from the customer's process. Without monitoring, the proprietary asset rots in place and the customer concludes the technology was never ready. Monitoring is the operational complement to RL specialization — the layer that lets the [[continual-learning-paradigm]] loop close.
- **[[vertical-ai-orchestration]].** Multi-agent orchestrators in industrial domains accumulate stickiness through operational history. Monitoring is the data substrate that history is built on: every alert, every drift event, every adaptation logged is a moat-deepening event the next vendor cannot reconstruct.
- **[[scaling-gap]].** The 74% / 16% scaling-gap evidence describes firms that cannot graduate AI past pilot. A non-trivial fraction of those failures are *monitoring-stack failures*: the pilot worked under controlled conditions and silently degraded in production because no one was watching. Monitoring is one of the operational ingredients the bull-managerial frame ([[foundational-enablers]]) treats as load-bearing without naming it as such.
- **[[ai-development-facilitator]] (Weber Pattern 2).** The middle of [[H2_u-curve-of-value]] where most tooling vendors die. Monitoring tools are exactly in this band, and the Protschky review finds the band is *empirically under-served* in 2025. There may still be a value pocket here for monitoring-specific tooling that implements the full 17-practice surface.

## Related

- [[protschky-ml-monitoring-2025]] — primary source.
- [[ml-production-environment-characteristics]] — C1–C5.
- [[ml-monitoring-quality-cycle]] — the 17 practices.
- [[ml-drift-types]] — concept / data / virtual / adversarial drift.
- [[rl-testing-validation]] — the pre-deployment counterpart in the [[H4_rl-specialization-value-pocket]] stack.
- [[eval-real-world-gap]] — the upstream framing.
- [[continual-learning-paradigm]] — the moat-deepening loop monitoring enables.
- [[H4_rl-specialization-value-pocket]] — where monitoring is the operational complement to RL specialization.
- [[vertical-ai-orchestration]] — where monitoring history is the substrate of operational stickiness.
- [[ai-development-facilitator]] — Weber Pattern 2; monitoring tools sit here.
- [[scaling-gap]] — the operational root cause of pilot failure.
- [[foundational-enablers]] — the WEF / Accenture frame within which monitoring is an implicit enabler.

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*
