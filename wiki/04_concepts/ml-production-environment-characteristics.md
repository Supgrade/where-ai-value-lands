---
title: ML Production Environment Characteristics (C1–C5)
status: emerging
tags:
  - concept
  - monitoring
  - protschky
  - production
  - vocabulary
last-updated: 2026-05-25
---

# ML Production Environment Characteristics (C1–C5)

> [!abstract] One-line
> The five structural characteristics — derived by [[protschky-ml-monitoring-2025]] from an interview study + multivocal literature review — that distinguish a deployed ML application's production environment from a conventional software application's, and that make ML monitoring a different problem from software monitoring.

The C1–C5 vocabulary is the **operational decomposition** of why ML applications fail in production in ways that conventional software does not. Each characteristic generates a specific class of monitoring failure mode and a specific set of monitoring practices that mitigate it (see [[ml-monitoring-quality-cycle]]).

## The five characteristics

### C1 — Data representation

An ML application's training data is only ever a *representation* of the real world. It does not contain every piece of information from the phenomenon it tries to model. Sensor coverage is partial, label quality is uneven, the long tail is undersampled by definition.

**Failure mode.** The model performs on the representation but fails on the real-world distribution that the representation under-covers. The classic case is the OOD-failure pattern in [[minerals-processing-optimization]] — the model is competent on the slice it was trained on and brittle the moment the chemistry, the ore composition, or the customer changes.

**Monitoring obligation.** Continuously test whether the live input distribution still matches the training distribution; flag the cases where it has drifted. See [[ml-drift-types]].

### C2 — Metrics as proxy

The metrics an ML system reports (accuracy, F1, AUC, MAPE, latency) are *proxies* for aspects of interest, not direct measurements of value. Accuracy on a hold-out set is not customer satisfaction. F1 on fraud detection is not avoided loss. A 95% prediction on machine wear is not a saved truck.

**Failure mode.** The metric improves and the business outcome does not — or worse, the metric improves and the business outcome degrades because the metric was over-optimised against. This is the operational instance of [[eval-real-world-gap]] and the "metric divergence" failure mode in [[rl-testing-validation]].

**Monitoring obligation.** Maintain a *metrics system* (not a single metric) that links technical, ML, and business measurements explicitly. See practice 3 in [[ml-monitoring-quality-cycle]].

### C3 — Assumptions

An ML application is built on assumptions about the world that may not hold: that customers behave roughly the same as last year, that sensors are calibrated, that the input schema is stable, that label noise is bounded, that the deployment topology won't change. Most of these assumptions are *implicit*, encoded into the training pipeline and the feature engineering rather than written down anywhere.

**Failure mode.** The world changes, the implicit assumption breaks, and the model fails in a way that the metric does not catch because the metric was constructed under the same assumption.

**Monitoring obligation.** Explicitly enumerate the assumptions in scope. Surface them to monitoring. Test for assumption violations (e.g., the feature unit has switched from Celsius to Fahrenheit). The "Define" step of the quality cycle is largely about making C3 visible.

### C4 — Changes

The production environment changes over time. New customers, new data sources, new regulation, seasonal demand, post-pandemic distribution shifts. Sometimes the change is sudden; more often it is slow and silent. **A static ML application in a moving world is a degrading ML application.**

**Failure mode.** Drift (see [[ml-drift-types]]). Concept drift (the relationship between inputs and outputs changes — e.g., what counts as fraudulent behaviour evolves), data drift (the inputs themselves shift), virtual drift (the inputs shift but the input-output relation holds).

**Monitoring obligation.** Drift detection is not optional; it is the load-bearing practice for C4. The Protschky synthesis devotes a dedicated monitoring practice (Practice 9) to drift detection specifically.

### C5 — Entanglement

ML applications exhibit *high entanglement*: every feature interacts with every other feature, the model interacts with the pipeline, the pipeline interacts with downstream services, the downstream services interact with the customer. Sculley et al.'s 2015 "CACE principle" — *Changing Anything Changes Everything* — is the canonical statement of this. There is no clean modular boundary inside an ML system.

**Failure mode.** A change in one place (a new feature, a retrained model, a schema update) silently degrades performance somewhere unrelated. Cause-effect attribution becomes nearly impossible without dedicated tooling.

**Monitoring obligation.** Cause-effect analysis (Practice 10), explainability methods (SHAP, LIME), dependency tracking, and version control across data + features + model + hyperparameters. C5 is the structural reason ML monitoring requires more discipline than software monitoring, not less.

## Why C1–C5 matter for *Where Value Lands*

The five characteristics are not just operational hygiene. They are structural features that determine which AI business archetypes can defend a moat:

- **A vendor selling an ML application that the customer has to monitor themselves** is selling an asset that will silently degrade in production. The customer either builds their own monitoring stack (expensive, requires skills they may not have — see [[ai-skill-shortage-as-diffusion-bottleneck]]) or watches the model rot. Either way, the value-creation-to-value-capture wedge widens against the vendor.
- **A vendor that bundles monitoring with the ML application** internalises C1–C5 as part of its product. The cost is real (vendor headcount, infrastructure, on-call rotation). The upside is that the customer's switching cost rises with every alert resolved, every drift caught, every adaptation made — see [[ml-monitoring]] and [[vertical-ai-orchestration]].
- **For [[H4_rl-specialization-value-pocket]] specifically**, every C-characteristic is sharper. C1 is sharper because the customer's process data is necessarily narrower than a generic foundation-model training set. C4 is sharper because the industrial process *is* the thing being adapted to. C5 is sharper because the harness is part of the moat. A vendor that ignores C1–C5 cannot make the H4 hypothesis work.

## Related

- [[protschky-ml-monitoring-2025]] — primary source.
- [[ml-monitoring]] — overview of the discipline.
- [[ml-monitoring-quality-cycle]] — the 17-practice surface that operationalises C1–C5.
- [[ml-drift-types]] — concept / data / virtual / adversarial drift; the operational form of C4.
- [[eval-real-world-gap]] — C2 is the operational decomposition of the eval-real-world gap.
- [[H4_rl-specialization-value-pocket]] — every C-characteristic is sharper for narrow industrial deployments.
- [[vertical-ai-orchestration]] — internalising C1–C5 is the operational pre-requisite.
- [[minerals-processing-optimization]] — canonical C1 / OOD failure example.
- [[predictive-maintenance]] — canonical C2 / C4 setting.
- [[ai-skill-shortage-as-diffusion-bottleneck]] — explains why SMEs cannot internalise C1–C5 themselves.

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*
