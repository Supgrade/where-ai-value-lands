---
title: RL — open vs closed source
status: reference
tags:
  - tech
  - reinforcement-learning
  - open-source
  - strategy
last-updated: 2026-05-24
---

# RL — open vs closed source

> [!abstract] One-line
> What's open and reproducible vs. what stays inside the frontier labs — and why the boundary is moving.

## The idea

Classical RL algorithms (PPO, DPO, GRPO, REINFORCE++) are well-published. Open libraries (Hugging Face TRL, OpenRLHF, verl, OpenInstruct, Verifiers) cover most of the orchestration surface. What stays *inside* the labs is increasingly **not** the algorithm but the recipe — curated datasets, reward-shaping schedules, value-function research, and the infrastructure for long-horizon agentic RL.

## The landscape (sketch)

**Open algorithms** — PPO, DPO, IPO, KTO, SimPO, GRPO, REINFORCE++. The pseudo-code fits on a page; the implementations are commodities.

**Open frameworks** — Hugging Face TRL, OpenRLHF, verl, OpenInstruct, Verifiers, TorchTune. Each one orchestrates the rollout / reward / update loop with reasonable defaults. None of them are the bottleneck.

**Open base models suitable for RL fine-tuning** — Llama-3, Qwen-2.5, Mistral, Gemma-2, DeepSeek-V3, and successors. Most are *open-weights* not *open-source* in the strict sense (the training data and recipe stay closed) — but the weights are enough to RL-fine-tune from.

**Closed** — the post-training recipes of frontier base models, OpenAI's o-series RL internals, Anthropic's production Constitutional AI runtime, Google's Gemini reasoning RL. Anything resembling [[value-functions-as-algorithmic-emotion]] is closed by construction. Long-horizon agentic RL infrastructure (the kind that powers multi-hour coding agents) is closed and is the live frontier.

## Strategic implication

The *algorithm* is commodity; the *recipe + the customer's data* is the moat. This is the same observation [[open-weight-asymmetry]] makes one floor up: commoditising a lower layer pushes capture upward into integration. See [[middle-layer-defensibility]].

## Where this fits in *Where AI Value Lands*

Under [[H4_rl-specialization-value-pocket]], the choice of **open vs closed base model** dictates whether the vendor owns the weights or rents them:

- **Owning the weights** (open-weight base + in-house RL) is the only path to [[continual-learning-paradigm]]-style compounding moat inside a single customer. The trained weights stay with the vendor; the customer's process data accumulates as IP.
- **Renting them** (RL on top of a closed frontier API — see [[rl-apis]]) is faster, cheaper, and disposable. Capability is better at t=0; defensibility is worse at t=24 months.

This is also the cleanest place to read [[H2_u-curve-of-value]]: the bottom of the U is the open algorithm + open weight + commodity GPU layer. The value travels upward, into whoever assembles those commodities against a customer's exclusive data.

## Related

- [[rlhf]]
- [[rlaif]]
- [[rl-from-verifiable-rewards]]
- [[rl-apis]]
- [[open-weight-asymmetry]]
- [[middle-layer-defensibility]]
- [[continual-learning-paradigm]]
- [[H1_L0-L7-ladder]]
- [[H2_u-curve-of-value]]
- [[H4_rl-specialization-value-pocket]]

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*
