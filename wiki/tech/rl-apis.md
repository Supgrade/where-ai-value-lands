---
title: RL APIs — the commercial fine-tuning surface
status: reference
tags:
  - tech
  - reinforcement-learning
  - apis
  - infrastructure
last-updated: 2026-05-24
---

# RL APIs — the commercial fine-tuning surface

> [!abstract] One-line
> The hosted services that let a non-lab actor run RL fine-tuning without building the infrastructure.

## The idea

Most boutique vendors and startups do not run their own RL infrastructure. They rent it from one of a small number of API providers. The choice of API determines, in order of strategic weight:

- **Which base models** are available — frontier closed-weight vs open-weight families.
- **Which training modes** are supported — SFT, DPO, full RLHF, verifier-based RL.
- **How data exclusivity is contracted** — does the provider train on the customer's data? does the customer get an exclusive endpoint?
- **How much of the weights the customer ever owns** — closed-weight tuning produces a tenant-scoped artifact the customer cannot extract; open-weight tuning can produce weights the customer keeps.

## The landscape (sketch, mid-2026 — indicative; specific products evolve fast)

**Frontier-lab tuning surfaces** (closed weights):

- **OpenAI** — fine-tuning across the GPT family, plus Reinforcement Fine-Tuning (RFT) with customer-supplied verifiers. Weights stay inside OpenAI.
- **Anthropic** — Claude custom-model and fine-tuning programs, historically in limited preview. Closed weights.
- **Google Vertex AI** — SFT and RLHF-style tuning on Gemini-family models. Closed weights.

**Open-weight tuning surfaces** (customer-controllable weights):

- **Together AI** — fine-tuning + dedicated endpoints on open-weight families.
- **Fireworks AI** — fine-tuning + low-latency serving for open-weight families.
- **Predibase** — LoRA / adapter-based fine-tuning at scale.
- **Modal / Replicate / RunPod** — raw compute for self-managed pipelines built on TRL, OpenRLHF, verl, etc.

**Verticalised / niche** — **Lamini**, **Anyscale** (Ray Serve + Ray RLlib heritage), and similar players targeting specific verticals or workloads.

## Where this fits in *Where AI Value Lands*

In [[H4_rl-specialization-value-pocket]], the API choice is the most concrete unit-economics decision a vendor makes:

- **RFT on a closed frontier base** — best base capability, weakest IP capture. No [[continual-learning-paradigm]] compounding inside a single customer because the weights never leave the provider.
- **Open-weight + Together / Fireworks** — full IP control, worse base capability per dollar at t=0. Compounding is possible because the vendor owns and re-trains the weights over the engagement.
- **Self-managed on Modal / RunPod** — maximum control, maximum operational burden. Only justified at scale.

The vendor's strategic posture in [[taker-shaper-maker]] (Taker rents, Shaper customizes, Maker trains) is largely encoded in this single choice. See [[ai-factory-huang]] for the underlying compute substrate all of these surfaces rent from.

## Related

- [[rlhf]]
- [[rlaif]]
- [[rl-from-verifiable-rewards]]
- [[rl-data-preparation]]
- [[rl-open-vs-closed-source]]
- [[ai-factory-huang]]
- [[taker-shaper-maker]]
- [[continual-learning-paradigm]]
- [[H4_rl-specialization-value-pocket]]

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*
