---
title: RLHF — Reinforcement Learning from Human Feedback
status: reference
tags:
  - tech
  - reinforcement-learning
  - alignment
last-updated: 2026-05-24
---

# RLHF — Reinforcement Learning from Human Feedback

> [!abstract] One-line
> Train a reward model from human preference comparisons over model outputs, then optimize the language model against that reward with PPO (or DPO as a single-stage variant).

## The idea

Collect `(prompt, completion_A, completion_B, human_choice)` triples from human labelers. Train a **reward model** that, given a prompt and a completion, predicts how much a human would prefer it. Then fine-tune the base language model by reinforcement learning against that reward — using the reward model as a proxy for the human.

Two practical wrinkles do most of the work:

- A **KL penalty** against the original supervised model keeps the RL-trained policy from drifting into degenerate, high-reward-but-incoherent text. The reward model is a proxy; the KL term keeps the proxy honest.
- The reward model in RLHF *is* a learned value function — see [[value-functions-as-algorithmic-emotion]] — but over terminal preferences (full completions) rather than intermediate trajectory states.

## How it works (sketch)

Three stages, classically:

1. **Supervised fine-tuning (SFT)** — fine-tune the base model on high-quality instruction–response pairs.
2. **Reward modeling** — collect human preference pairs, train a Bradley-Terry-style reward model.
3. **RL fine-tuning** — optimize the SFT model against the reward model with PPO, with a KL penalty against the SFT model.

**DPO (Direct Preference Optimization)** collapses steps 2 and 3 into a single contrastive loss directly on the preference data — no explicit reward model, no sampling-based RL loop. Cheaper, more stable, often comparable quality. The successor variants (IPO, KTO, SimPO) sit in the same family.

## A canonical example

**InstructGPT** (Ouyang et al., 2022) — the recipe behind ChatGPT. Anthropic's **HH-RLHF** dataset (Helpful and Harmless) is the canonical open analogue. Most subsequent aligned chat models — Claude, Gemini, the Llama-Instruct line — are descendants of this template, with variations in the data mix and the loss function.

## Where this fits in *Where AI Value Lands*

RLHF is the production recipe behind every major aligned chat model. It is the **floor** the author's hypothesis stands on: [[H4_rl-specialization-value-pocket]] is a bet that the same recipe, applied to narrow industrial domains with proprietary preference data, captures durable value. The hypothesis depends on whether the *human-preference labeling step* — which is what makes RLHF expensive and slow — can be either narrowed (a small panel of domain experts) or partially replaced ([[rlaif]], [[rl-from-verifiable-rewards]]) without losing the production quality the frontier labs achieve.

## Related

- [[rlaif]]
- [[rl-from-verifiable-rewards]]
- [[rl-data-preparation]]
- [[rl-testing-validation]]
- [[value-functions-as-algorithmic-emotion]]
- [[H4_rl-specialization-value-pocket]]

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*
