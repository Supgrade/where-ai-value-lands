---
title: RL from Verifiable Rewards (RLVR)
status: reference
tags:
  - tech
  - reinforcement-learning
  - reasoning
last-updated: 2026-05-24
---

# RL from Verifiable Rewards (RLVR)

> [!abstract] One-line
> Replace the learned reward model with a *deterministic* check — does the unit test pass? does the theorem prove? did the simulation match ground truth? — and run RL against that signal directly.

## The idea

When an objective truth function exists for a task, the reward-model layer is unnecessary and the noise it introduces vanishes. RLVR has powered the post-2024 reasoning-tuned model wave (OpenAI o1, DeepSeek R1, and successors). It is the technical mechanism behind the agentic coding agents the wiki repeatedly cites — hours-long orchestration of sub-agents that solve software-engineering problems by generating, testing, and iterating against compilers and test suites.

The trade is favourable wherever a verifier exists. The hard question is: for which domains can one be *constructed*?

## How it works (sketch)

- For each problem, sample N completions from the policy model.
- Run the verifier on each completion: reward = 1 if it passes, 0 otherwise (or a richer signal if partial credit is defined).
- Policy-gradient update: PPO, **GRPO** (Group Relative Policy Optimization, the DeepSeek R1 variant), or REINFORCE++.
- Sample efficiency improves dramatically when sampling is over large search trees — test-time compute meets training-time RL. See [[agentic-scaling-law]].

The mechanism is conceptually the same as classical RL on games (AlphaZero's win/loss signal); the breakthrough is that for code and math the verifier is *cheap and abundant*, so the technique scales.

## A canonical example

- **DeepSeek-R1** — GRPO on math and code with deterministic checkers; the first widely reproduced reasoning recipe.
- **OpenAI o1 / o3** — closed-source but openly characterized as RL on verifiable reasoning traces.
- **AlphaProof** (DeepMind) — RL on a formal theorem prover (Lean) as the verifier.

## Where this fits in *Where AI Value Lands*

This is the **load-bearing technical claim under [[H4_rl-specialization-value-pocket]]**. The hypothesis depends on whether a verifiable reward can be *constructed* for industrial / B2B processes:

- For **software**: trivial — unit tests, type checks, integration tests.
- For **protein folding or materials science**: clear — energy minima, structural match against experiment.
- For **"did this energy-retrofit proposal actually improve the plant's KPI three months after deployment?"**: the loop is long, noisy, contestable, and entangled with confounders the model cannot observe. Sparse, delayed reward is the open problem (see [[value-functions-as-algorithmic-emotion]]).

The vertical map of which industries admit a verifier and which do not is roughly the vertical map of where domain-RL startups can compound and where they cannot.

## Related

- [[rlhf]]
- [[rlaif]]
- [[agentic-scaling-law]]
- [[value-functions-as-algorithmic-emotion]]
- [[continual-learning-paradigm]]
- [[rl-data-preparation]]
- [[H4_rl-specialization-value-pocket]]

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*
