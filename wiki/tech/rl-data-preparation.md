---
title: RL data preparation
status: reference
tags:
  - tech
  - reinforcement-learning
  - data-pipeline
last-updated: 2026-05-24
---

# RL data preparation

> [!abstract] One-line
> The pipeline that turns raw model outputs, human or AI judgements, or simulator transcripts into a training signal: trajectory collection, dedup, contamination filtering, reward shaping, preference balancing.

## The idea

RL fine-tuning is downstream of a very dirty data process. Most of the engineering effort in production RL is *not* the algorithm — it is the pipeline. For a domain-specific RL deployment, this is where most of the cost and risk lives.

A clean RL paper makes the data sound like a given. In production, the data is the project.

## The pipeline (sketch)

- **(a) Trajectory collection.** Sample many completions per prompt. For online RL, this is continuous and tied to the live policy. For offline RL, it's a one-time scrape.
- **(b) Preference / reward labeling.** Human labelers ([[rlhf]]), AI judges ([[rlaif]]), or deterministic verifiers ([[rl-from-verifiable-rewards]]).
- **(c) Deduplication.** Exact and near-duplicate trajectories distort the preference distribution and let the model overfit to one phrasing.
- **(d) Contamination filtering.** Held-out evals must not leak into training data. This is where most "too-good-to-be-true" benchmark numbers come from — a single fuzzy-matched eval question in the training set inflates the published score.
- **(e) Reward shaping.** Partial credit, intermediate signals (process reward models, step-wise verifiers), discount factor selection, KL coefficients. This is the most underspecified step in public literature; see [[value-functions-as-algorithmic-emotion]] for the upstream problem.
- **(f) Balancing.** Preference data skewed toward one stylistic register or one labeler's bias collapses the post-RL model to that style — chatty when it should be terse, hedged when it should be decisive.

## A canonical example

Anthropic's **HH-RLHF** dataset construction; OpenAI's **WebGPT** data pipeline; the published preference datasets in the **OpenAssistant** project. The patterns are reasonably documented; the *recipes* used in production remain proprietary.

## Where this fits in *Where AI Value Lands*

For [[H4_rl-specialization-value-pocket]], the entire customer engagement is largely a data-pipeline engagement. The startup's first 6–18 months on a customer site are: instrumenting the process, capturing trajectories, labeling outcomes, building the verifier where one is constructible. This is closer to a [[vertical-ai-orchestration]] services engagement than to a frontier-lab RL run — and the unit economics, defensibility, and gross margins look like it.

It also means the **moat compounds in the data layer, not the algorithm layer**. The customer's instrumented process — once labelled and clean — is much harder to copy than the RL training run that consumes it. See [[continual-learning-paradigm]] for the longer-horizon version of this point.

## Related

- [[rlhf]]
- [[rlaif]]
- [[rl-from-verifiable-rewards]]
- [[rl-testing-validation]]
- [[continual-learning-paradigm]]
- [[value-functions-as-algorithmic-emotion]]
- [[vertical-ai-orchestration]]
- [[H4_rl-specialization-value-pocket]]

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*
