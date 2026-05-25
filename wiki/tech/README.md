---
title: Tech — reference layer
status: living
tags:
  - tech
  - index
last-updated: 2026-05-24
---

# Tech — reference layer

> [!abstract] One-line
> Short technical explainer pages that ground the analytical concepts in `04_concepts/` and the hypotheses in `02_hypothesis/` in real algorithmic detail.

These pages are the technical floor under the analytical concepts in `04_concepts/` and the hypotheses in `02_hypothesis/`. They aim for clarity, not completeness — just enough that an operator can weigh the hypotheses above.

## Catalog

- [[rlhf]] — Reinforcement Learning from Human Feedback. Preference data → reward model → PPO-style updates. The OpenAI / Anthropic / Google production recipe behind aligned chat models.
- [[rlaif]] — Reinforcement Learning from AI Feedback. Replace the human labeler with a strong model labeler (Constitutional AI; Llama-Guard-style judges).
- [[rl-from-verifiable-rewards]] — RLVR. Reward is a deterministic checker (unit-test passing, theorem-prover success, simulator outcome). The recipe behind reasoning-tuned models (o1, R1).
- [[rl-data-preparation]] — the offline / online data pipeline: trajectory collection, preference pair curation, deduplication, contamination, reward shaping. The dirty work.
- [[rl-testing-validation]] — held-out eval design, reward hacking detection, regression dashboards, human spot-checks, the eval / real-world gap problem.
- [[rl-open-vs-closed-source]] — what's open (PPO, DPO, GRPO, TRL, OpenRLHF, verifiers libraries) vs what stays closed (frontier RL recipes, value functions). Strategic implications.
- [[rl-apis]] — the commercial fine-tuning surface: OpenAI fine-tuning + RFT, Anthropic custom models, Google Vertex tuning, Together, Fireworks, Predibase, Modal-hosted TRL.
- [[ml-monitoring]] — the production-time monitoring discipline; the operational counterpart to [[rl-testing-validation]]. Five production-environment characteristics (C1–C5) + 17 monitoring practices on a quality-management cycle, from [[protschky-ml-monitoring-2025]]. See also [[ml-production-environment-characteristics]], [[ml-monitoring-quality-cycle]], [[ml-drift-types]].

## How this folder relates to the hypotheses

These pages are the technical layer under [[H4_rl-specialization-value-pocket]] — the working hypothesis that RL-driven domain-specific fine-tuning is a real value pocket. Whether that bet is correct depends on facts that live here: what reward signals can be constructed, what data pipelines are tractable, what's reproducible in open code vs locked inside frontier labs, which hosted API a vendor chooses to rent — and, critically, whether the production-time monitoring stack ([[ml-monitoring]]) catches drift before the customer's process engineers do. The pages above let an operator inspect those facts directly rather than taking the analytical layer's word for it.

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*
