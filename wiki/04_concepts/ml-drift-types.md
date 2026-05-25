---
title: ML Drift Types
status: emerging
tags:
  - concept
  - monitoring
  - drift
  - protschky
last-updated: 2026-05-25
---

# ML Drift Types

> [!abstract] One-line
> A model degrades in production not because it forgot what it learned but because *the world changed around it*. Drift detection — the operational instance of [[ml-production-environment-characteristics]] **C4 — Changes** — is the load-bearing practice that catches the change before the business KPI does.

[[protschky-ml-monitoring-2025]] formalises four drift types in its Practice 9. The distinction matters because the underlying mechanism differs, the failure mode differs, and the appropriate adaptation (in Practice 11) differs.

## The four drift types

### Concept drift — p(y|x) changes, p(x) may not

The *relationship* between inputs and outputs changes. What counts as fraud in 2024 may not count as fraud in 2026; the input features are the same, but the labelling rule shifted. What predicted customer churn pre-pandemic may not predict it post-pandemic.

**Detection signal.** Accuracy on freshly-labelled production data degrades even though the input distribution is stable. Hard to catch without ground truth.

**Adaptation.** Almost always requires retraining on freshly-labelled data; rule changes propagate slowly through historical data.

### Data drift — p(x) changes, p(y|x) may not

The *input distribution* shifts. New customers, new sensor types, new geographies, seasonal demand. The relation between features and labels may still hold; the feature distribution has moved out of the training-data envelope.

**Detection signal.** Statistical tests on input distributions (KS test, PSI, JS divergence, Wasserstein distance) flag distributional change. Available *without* ground truth — which is why this is the most-instrumented drift type in production monitoring.

**Adaptation.** Sometimes retraining; sometimes rebalancing; sometimes scoping the model down to where it's still valid.

### Virtual drift — p(x) changes, p(y|x) holds

The input distribution shifts but the input-output relation is preserved. This is the *benign* case — a metric may look bad on aggregate while still being fit for purpose.

**Detection signal.** Drift detector fires on inputs; accuracy on freshly-labelled samples holds. The interpretation matters: virtual drift is the case where you *should not* retrain — retraining wastes compute and may introduce regression.

**Adaptation.** Often none required. The point of distinguishing this from data drift is to *avoid acting* when no action is needed. Many monitoring stacks fail by treating virtual drift as data drift and retraining unnecessarily.

### Adversarial drift — malicious data injection

Someone is deliberately corrupting inputs to degrade the model or trigger a specific misprediction. Data poisoning, prompt injection, evasion attacks. Distinct from the first three because it is *intentional* and *adaptive* — the adversary is updating their attack in response to your defences.

**Detection signal.** Anomaly patterns that look statistically plausible but cluster around model boundaries; correlated attacks across customer accounts; sudden behavioural shifts that don't follow seasonal or business logic.

**Adaptation.** Treats drift as a security problem, not a data-quality problem. Adversarial training, input sanitation, rate-limiting, in extreme cases model substitution and out-of-band investigation.

## How drift types interact with the production environment characteristics

| Drift type | Most binding characteristic | Why |
|---|---|---|
| Concept drift | C3 (Assumptions), C4 (Changes) | The model's implicit assumption about the input-output rule is broken by environmental change |
| Data drift | C1 (Data representation), C4 | Training data under-covers a part of the distribution that now matters |
| Virtual drift | C1, C2 (Metrics proxy) | Inputs move but the proxy still tracks reality; over-reaction is the failure mode |
| Adversarial drift | C5 (Entanglement) | Attack surface compounds across components; cause-effect analysis is hard |

## Examples from the wiki's industrial setting

- **[[predictive-maintenance]].** Wear patterns shift as feedstock changes or maintenance schedules drift — data drift. New failure modes emerging in machinery that wasn't in the training set — concept drift.
- **[[minerals-processing-optimization]].** New ore composition, new chemistry — data drift, but at a magnitude where the model is OOD and effectively useless until retrained. The canonical OOD example in [[deloitte-ai-dossier-eri]].
- **[[grid-optimization]].** New renewable mix, new demand patterns post-EV adoption — concept drift in dispatch behaviour; data drift in the demand side.
- **[[hydrocarbon-reservoir-exploration]].** New basins, different seismic noise profiles — pure data drift.
- **Fraud detection (a non-wiki canonical case).** New fraud schemes invented by adversaries — concept drift + adversarial drift simultaneously.

## Why this matters for *Where Value Lands*

Drift detection is the operational practice that determines whether [[continual-learning-paradigm]] is feasible at all. A monitoring system that cannot distinguish virtual drift from data drift will either over-retrain (burning compute, introducing regression) or under-retrain (letting the model decay silently). The vendor who can correctly classify drift types in a customer's domain is the vendor whose retraining loop converges; the vendor who cannot, is in margin-destroying services-revenue mode.

For [[H4_rl-specialization-value-pocket]] specifically, drift is the *binding* operational risk. The proprietary model deployed inside the customer faces drift on the customer's specific process — and the vendor's defensibility depends on detecting it before the customer's process engineers do.

## Related

- [[protschky-ml-monitoring-2025]] — primary source (Practice 9).
- [[ml-monitoring]] — overview discipline.
- [[ml-production-environment-characteristics]] — C4 is the structural driver of drift.
- [[ml-monitoring-quality-cycle]] — Practice 9 in the cycle.
- [[continual-learning-paradigm]] — drift detection enables the retraining loop.
- [[H4_rl-specialization-value-pocket]] — drift is the binding operational risk.
- [[predictive-maintenance]], [[minerals-processing-optimization]], [[grid-optimization]], [[hydrocarbon-reservoir-exploration]] — industrial drift settings.
- [[rl-testing-validation]] — pre-deployment counterpart; distribution-shift checks belong here.

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*
