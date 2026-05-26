---
title: ML Monitoring Quality Cycle (17 practices)
status: emerging
tags:
  - concept
  - monitoring
  - protschky
  - operational-framework
  - vocabulary
last-updated: 2026-05-25
---

# ML Monitoring Quality Cycle (17 practices)

> [!abstract] One-line
> Seventeen ML monitoring practices, arranged by [[protschky-ml-monitoring-2025]] on a five-step quality-management cycle (define → measure → assess → act → control) with three cross-sectional practices, derived from a multivocal literature review + 10 expert interviews + 15-tool review.

The 17 practices are the **operational surface** of ML monitoring: the discrete things a monitoring entity must do to keep an ML application alive in production. They are arranged sequentially on a quality-management cycle so that the cycle's output (control) feeds back into the next cycle's input (define) — making continuous improvement structurally explicit. Three additional practices are cross-sectional (applied across all steps).

Mapping to [[ml-production-environment-characteristics]] (C1–C5) is given where the source identifies a specific influence.

## Step 1 — Define the relevant problem and improvement areas

**Practice 1. Define the ML application's weaknesses and compensatory workflows.** Enumerate the failure modes the application is *known* to have (errors are not eliminable, only managed; see C1). Define the compensatory workflows that take over when the model is wrong. The FMEA (Failure Mode and Effects Analysis) from classical quality management is the canonical methodology. *Maps to C1.*

**Practice 2. Select appropriate metrics from the range between technical and organisational ones.** Cover computational (latency, CPU), ML (accuracy, F1), business-driven (e.g., loss avoided in fraud, downtime avoided in predictive maintenance), and strategic (revenue, satisfaction) metrics. Different stakeholders need different layers.

**Practice 3. Model a metrics system for the selected technical and organisational metrics.** A *system* — explicit tradeoffs and preferences across metrics — rather than a flat list. Critical because no single metric captures value (C2, C5). *Maps to C2, C5.*

## Step 2 — Collect and process the relevant data and metrics

**Practice 4. Collect metadata from the ML application's context.** Versions of data, model, hyperparameters; pipeline configuration; trace IDs; session metadata. ML versioning is more complex than software versioning because of entanglement (C5). *Maps to C5.*

**Practice 5. Collect the ground truth label, if it is available.** Three sub-activities: assess ground-truth availability (delay? changed-reality? labelling cost?); implement labelling mechanisms (human-in-the-loop, post-hoc verification); avoid over-burdening the user with confirmation tasks. *Maps to C1.*

**Practice 6. Collect metrics data for the ML application.** Computational, standard ML, business-layer. Sample at an interval long enough to avoid over-engineering, short enough to catch the issue before it propagates. Dock the business-intelligence system to the monitoring system so business metrics co-exist with technical metrics. *Maps to C2.*

**Practice 7. Process the collected data and metrics for assessment.** When ground truth is unavailable, use statistical metadata (input distributions, missing-value rates, class distributions, confidence histograms) as a proxy. Behavioural metrics — what the model is *doing* — substitute for accuracy when accuracy can't be measured live. *Maps to C2.*

## Step 3 — Assess causes, impacts, and other influencing factors

**Practice 8. Investigate the collected data and metrics to identify data quality issues.** NaN / missing values, schema breaks, unit changes (Celsius → Fahrenheit), outliers, anomalies, threshold violations. Check fairness metrics on data slices, not just on aggregates. *Maps to C2, C3.*

**Practice 9. Investigate the collected data and metrics to identify (adversarial) drifts.** Drift detection. Differentiate concept drift, data drift, virtual drift, and adversarial drift (see [[ml-drift-types]]). Drift is the load-bearing operational instance of C4. *Maps to C4.*

**Practice 10. Conduct cause-effect analysis for identified data quality issues and drifts.** Trace causes through entangled components — feature engineering, model, downstream services, business metric. Distinguish model faults from external exceptions (and act differently on each). SHAP / LIME for interpretability. Determine the cause's impact on business KPIs to prioritise remediation. *Maps to C5.*

**Practice 11. Determine adaptations for identified data quality issues and drifts.** Decide *what* to change: retrain, model-substitute, rollback, parameter tweak, harness change. Compare against prior adaptations (using version metadata). Consider tradeoffs against other adaptations. *Maps to C3, C5.*

## Step 4 — Act to realise improvements

**Practice 12. Communicate the adaptations to stakeholders.** Dashboards, visualisations, plain-language explanations for non-ML stakeholders. Education across the organisation matters: data literacy is low in most enterprises, so the monitoring entity has to translate. *Maps to C1, C5.*

## Step 5 — Control the preceding steps in the long term

**Practice 13. Verify the adaptations made in the ML application from the act step.** Did the change actually produce the expected improvement? Failing adaptations may require rapid rollback. *Maps to C4, C5.*

**Practice 14. Transfer the required adaptations in the monitoring process to the define step.** Loops back. New measurement needs surfaced during the cycle become inputs into the next define step. *Maps to C2, C4.*

## Cross-sectional practices (applied across all 5 steps)

**Practice 15. Apply proactive mechanisms.** Catch issues before they fully unfold. Activities such as metric selection, insight assessment, and action derivation should always be proactive — though there will always be aspects the monitoring entity has not anticipated, so reactive mechanisms remain necessary too. *Maps to C2.*

**Practice 16. Iteratively and continually learn from the production environment.** Mindset shift: ML applications never reach a "complete" state. Establish a *virtuous cycle* in which the monitoring loop generates training signal, the model improves, scope expands, more signal accumulates. This is the operational form of [[continual-learning-paradigm]]. *Maps to C1, C4.*

**Practice 17. Design monitoring tailored to use cases.** No off-the-shelf monitoring system covers every embedding (cloud vs on-device vs TinyML), every use-case type, every iteration cadence. The monitoring system itself should be more modular and flexible than the application — and *less complex than the application*. Expert 08: "if this monitoring system is constantly sending alerts, there is something not working — either the monitoring system or the model."

## What this changes for *Where Value Lands*

The 17 practices are a **detailed bill of materials** for what it actually takes to run an ML application in production. Two implications:

- **Cost-of-operation realism.** Most external estimates of AI deployment cost ignore the practices below the model layer. The [[scaling-gap]] literature is partially explained by this: firms that pilot a model without budgeting for Practices 5–11 watch the pilot fail in production and conclude the model was bad.
- **Build vs buy for monitoring tooling.** A monitoring vendor that genuinely implements the full surface (especially 5, 7, 8, 9, 10, 16) is selling a product the customer cannot easily replicate from open-source primitives. This is the empirical wedge under [[ai-development-facilitator]] — the squeezed middle of [[H2_u-curve-of-value]] — where a specialised tool could still survive.

## Related

- [[protschky-ml-monitoring-2025]] — primary source.
- [[ml-monitoring]] — overview discipline.
- [[ml-production-environment-characteristics]] — C1–C5; the structural drivers behind the practices.
- [[ml-drift-types]] — operational expansion of Practice 9.
- [[rl-testing-validation]] — pre-deployment counterpart to Practices 8–13.
- [[continual-learning-paradigm]] — Practice 16 is its operational instantiation.
- [[scaling-gap]] — under-budgeted monitoring as a root cause of pilot failure.
- [[ai-development-facilitator]] — where a monitoring tool that implements this surface could survive.
- [[foundational-enablers]] — the enterprise-side framing within which these practices are an implicit enabler.
- [[ai-first-company-loop]] — the *firm-level* sibling of this cycle. Protschky scaffolds production discipline for *one ML application*; the five-layer loop scaffolds production discipline for *the entire company*. The two nest: a firm running the loop contains N Protschky-monitored ML applications, and the loop's Layer 5 (learning) has each application-level cycle as part of its input. Reading the YC framing on top of Protschky gives it empirical floor; reading Protschky inside the YC framing gives it firm-level operating-model scope.

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*
