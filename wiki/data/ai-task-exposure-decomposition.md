---
title: AI task exposure decomposition (Acemoglu)
type: table
source-primary: Acemoglu, *The Simple Macroeconomics of AI*, NBER WP 32487 (May 2024)
source-via: "[[acemoglu-simple-macroeconomics]]"
year: 2024
related:
  - task-based-framework
  - task-based-tfp-ceiling
  - capital-labor-divergence
last-updated: 2026-05-22
---

# AI task exposure decomposition

## The data

| Quantity | Value |
|---|---|
| US labor tasks theoretically exposed to gen AI | ~19.9% |
| Of those, share profitably automatable in 10 years | ~23% |
| → All US tasks profitably automatable | ~4.6% |
| Average task-level cost saving on automatable tasks | ~15.4% |
| Resulting 10-year US TFP gain (upper bound) | **0.55–0.71%** cumulative |
| 10-year US GDP gain (upper bound) | **0.9–1.6%** cumulative |

The arithmetic: aggregate gain ≈ 4.6% × 15.4% ≈ 0.71% cumulative TFP over 10 years (Hulten's theorem).

## Source

Daron Acemoglu, *The Simple Macroeconomics of AI*, NBER Working Paper 32487, May 2024. Surfaced through [[acemoglu-simple-macroeconomics]].

## What it shows

The full intermediate decomposition behind the bear-case TFP ceiling. The 4.6% number — the share of US tasks profitably automatable in a decade — is the load-bearing figure. The 15.4% cost-saving estimate is conservative; the 4.6% exposure figure is what makes the aggregate small.

Sensitivity is real: deployment cost, verification overhead, and the easy-vs-hard-to-learn distinction can all move the numbers materially. But the order of magnitude survives most reasonable perturbations of the assumptions.

## How to cite

> *Acemoglu (2024) decomposes the US task base as 19.9% exposed × 23% profitably automatable → 4.6% of all tasks automatable, with ~15.4% average task-level cost savings.*

## Connections

- [[task-based-framework]] — the concept page this table sits inside.
- [[task-based-tfp-ceiling]] — the aggregate ceiling derived from these inputs.
- [[capital-labor-divergence]] — same decomposition supplies the labor-displacement projection.
- [[scaling-wall]] — the architectural argument for why the 23% profitability figure may *also* be optimistic.
- [[acemoglu-simple-macroeconomics]] — primary source.
