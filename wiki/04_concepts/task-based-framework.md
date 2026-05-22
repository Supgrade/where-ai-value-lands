---
title: Task-Based Economic Framework (Hulten's theorem, easy vs hard-to-learn)
status: emerging
tags:
  - concept
  - economics
  - productivity
  - labor
  - bear-case
last-updated: 2026-05-21
---

# Task-Based Economic Framework

> [!abstract] One-line
> A formal labor-economics framework for **bounding aggregate AI productivity gains** from below by decomposing output into tasks, then asking which tasks are *exposed*, which are *profitably automatable*, and how *easy* each is to learn statistically.

## The framework
Aggregate output is the execution of a sequence of tasks, each allocated either to human labor or to automated capital. Under standard assumptions, **Hulten's theorem** says that aggregate productivity gains are roughly:

> *(fraction of tasks impacted) × (average task-level cost saving)*

That is — even a technology that is impressive at the task level only moves the macro needle in proportion to how much of the economy it touches *and* how much cost it removes when it does.

## The numbers (per [[acemoglu-simple-macroeconomics]] as cited in [[bear-case-synthesis]])
| Quantity | Value |
|---|---|
| US labor tasks theoretically exposed to gen AI | ~19.9% |
| Of those, share profitably automatable in 10 years | ~23% |
| → All US tasks profitably automatable | ~4.6% |
| Average task-level cost saving on those tasks | ~15.4% |
| Resulting 10-year US TFP gain (upper bound) | **0.55–0.71% cumulative** |
| 10-year US GDP gain (upper bound) | **0.9–1.6% cumulative** |

For comparison, optimistic forecasts (McKinsey, GS Economists) put 10-year US productivity gains at ~9% cumulative — **>10× higher**.

## Easy-to-learn vs. hard-to-learn tasks
A critical refinement. Tasks differ in how learnable they are by current AI architectures:

- **Easy-to-learn**: objective performance metric, clear input → output mapping, abundant training data. Examples: code autocomplete, document summarization, ad copy drafting.
- **Hard-to-learn**: context-dependent judgment, multi-variate decisions, physical-world intuition, reliance on tacit/historical experience. Examples: novel project planning, cross-functional negotiation, complex medical diagnosis, M&A judgment.

Empirical productivity gains from gen AI are derived almost exclusively from easy-to-learn tasks. Hard-to-learn tasks are where most enterprise value lives, and they are precisely the tasks the [[scaling-wall]] makes hardest to automate. Adjusting for this friction pulls the TFP ceiling down from ~0.71% to **<0.55%** cumulative over 10 years.

## Two corrosive corollaries
1. **GDP can rise while welfare falls.** Gen AI lowers the cost of socially-negative tasks (SEO spam, manipulation, deepfakes, exploitative ads). These show up as productive activity in GDP while degrading welfare. See [[capital-labor-divergence]].
2. **Productivity gains for low-skill workers accelerate their displacement.** When AI most helps the entry-level worker, it *also* makes their role most replaceable — and the displaced labor floods the unautomated remainder, driving wages down across the lower distribution.

## Why this might be wrong
- The 19.9% / 23% / 15.4% numbers are model-dependent estimates; sensitivity to assumptions about cost-of-deployment and verification overhead is high.
- The framework holds aggregate output structure fixed. If AI enables **new tasks** (genuinely human-complementary), the bound is conservative.
- Hard vs easy may be the wrong axis. Test-time compute, agent harnesses, and specialized scaffolding can move tasks across the boundary over time.

## Data
- [[task-based-tfp-ceiling]] — the <0.71% cumulative TFP ceiling.
- [[ai-task-exposure-decomposition]] — the full 19.9% / 23% / 4.6% / 15.4% decomposition table.

## Related
- [[acemoglu-simple-macroeconomics]]
- [[bear-case-synthesis]]
- [[scaling-wall]]
- [[capital-labor-divergence]]
- [[H2_u-curve-of-value]]
- [[wef-ai-in-action-2025]] — $7.6–17.9T bull projection in direct tension with the <0.71% TFP ceiling this framework derives.
- [[oecd-sme-ai-adoption-2025]] — OECD G7 SME source: macro projection of 0.2–1.3 pp annual labour-productivity gain is in tension with Acemoglu's <0.71% cumulative cap; the two views remain unreconciled.
- [[ai-productivity-firm-level]] — firm-level productivity-premium evidence relevant to whether macro projections close to the cap.
- [[oecd-g7-productivity-gain-projection]] — the specific 0.2–1.3 pp figure to weigh against the cap.
