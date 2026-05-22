---
title: Contributor Charter
status: draft
tags:
  - planning
  - collaboration
  - contribution
last-updated: 2026-05-23
---

# Contributor Charter

A high-bar standard for what counts as a good contribution to this wiki. The charter exists so a contributor knows the merge bar before spending time, and so the author can close PRs by reference rather than re-explanation.

This document is draft. It will mutate as real contributions accumulate and the actual failure modes become visible.

## The merge bar

Most PRs are closed, not merged. The author rejects more than accepts, especially early. This is intentional: the wiki's value is the coherence of one author's reading of the field, and every additional contributor is a small dilution. The merge bar is the only enforcement mechanism.

A PR is in scope if it:

- Touches an active research question or a working hypothesis in a way the wiki does not already cover.
- Brings new evidence, not new opinion.
- Reads in the same voice as the rest of the wiki — English, present tense, precise, no marketing language.
- Follows the file conventions in [[CLAUDE]] (slugs, frontmatter, wikilinks both directions).

A PR is closed if it:

- Restates frames already in the wiki without new lift.
- Argues a position without evidence the author can verify.
- Reorganizes structure (renames, splits, merges, deletes) — those are author-only operations via [[edit]], not contribution targets.
- Pulls the wiki toward topics outside the paper's scope.

## What we want

The four contribution kinds, in descending order of expected volume:

- **Sources we do not have.** Papers, articles, books, datasets, primary documents. Drop a stub in `raw/` with the citation, the URL or local path, a one-line reason it bears on the research, and the two or three wiki pages you think it touches. The author runs [[ingest]] post-merge.
- **Daily thoughts from operators.** Your own stream-of-consciousness reasoning about the research questions, written from inside the operator role. Lands in `raw/daily tougths/` as `YYYY-MM-DD_<your-handle>.md`. The author may engage with it through [[reflect]] post-merge — selective promotion, not automatic ingestion.
- **Concept refinements that touch open questions.** New concept pages in `wiki/04_concepts/`, or sharpening of existing ones. Frontmatter must be complete. At least two wikilinks to existing pages. Status starts at `draft`.
- **Sharpened open questions.** Single clean question with a one-line rationale, proposed under an appropriate section of [[05_open-questions]]. Useful when you can see a question the wiki should be asking but is not.

## What we do not want

Out of scope, unless you can show direct bearing on where AI value lands for capital-rich operators:

- Embodied AI and robotics.
- Consumer AI and chat assistants as a primary subject. (Where consumer dynamics drive frontier-lab economics, ingest as evidence of the substrate layer — not as a category in its own right.)
- ML research and novel technical contributions.
- General AI safety and alignment debates.
- Personal-experience essays without a structural claim.
- Surface-level summaries of widely-shared frames (the bull paradigm, the bear paradigm, the geopolitics tripartite) without new lift.

If your contribution is "I think this is interesting and the wiki should cover it" without a hook into an existing hypothesis or open question, open a GitHub issue first.

## Evidentiary standards

- **Every non-trivial claim has a source.** Either a wikilink to an existing source page in `wiki/05_sources/`, or — if the source is new — a stub in `raw/` that the author will turn into a source page on merge.
- **Quantitative claims have a data page.** Numbers live in `wiki/data/` as one-claim-per-file, with `source-primary`, `source-via`, and `year` frontmatter. Inline numbers in concept pages link out to the data page.
- **Secondary syntheses are flagged as such.** If your contribution is a synthesis of an LLM-generated digest, a Twitter thread, or a podcast summary, say so on the source page. Secondary syntheses are useful but they are not the same as primary sources.
- **Engage with the contrary frame.** If you contribute evidence supporting [[H2_u-curve-of-value]], note where the bear-case sources ([[bear-case-synthesis]], [[zitron-circular-economics]], [[acemoglu-simple-macroeconomics]], [[marcus-world-models-failure]]) push back, or why they do not apply. The wiki is structured around tension, not consensus.

## Voice

- English. Present tense. Precise.
- No marketing language. No hype. No exclamation marks. No emoji anywhere.
- Italian terms preserved in parentheses where the English translation loses weight.
- Strong claims welcomed if they carry a citation or are explicitly labeled as bets.
- Peer-to-peer with smart operators. Not for the general public. Not for ML researchers.

The voice calibration is in [[01_audience]]. Re-read it if a draft starts drifting into either explainer mode or research-paper mode — neither is correct.

## Forward → reverse link rule

If your contribution links page A to page B, page B must reference page A back. The reverse link is added in the same PR, not deferred to a future cleanup pass.

The `/contribute` skill runs a forward → reverse link check before opening the PR. If it flags a missing reverse link, you either add it on the target page or accept the lint warning, which the author will see during review.

## Per-page contributor credit

When a contributor's work materially shapes a wiki page, that page gets a small `Contributors:` line in its frontmatter or in a footer block:

```
Contributors: <name-or-handle> (concept introduction), <name-or-handle> (source ingest)
```

This is in addition to the top-level [[CONTRIBUTORS]] file at the repository root. The roll lists everyone with at least one merged PR; the per-page line is for substantive shaping of that specific page.

Daily thoughts in `raw/daily tougths/` retain the contributor's handle in the filename and remain attributable through git history; no separate frontmatter line is needed.

## How to contribute

The mechanical path is in [[06_collaboration]] §T1. The skill is at `.claude/skills/contribute/SKILL.md`. The contributor-facing entry document is the repository root [`CONTRIBUTING.md`](../../CONTRIBUTING.md).

Order of operations from the contributor's side: fork → open in agentic CLI → run [[contribute]] → branch → PR → wait for review.

## Friction is the feature

Contributing requires a CLI, a git workflow, and willingness to run an agentic skill against your fork. This is deliberate. A founder or operator who can run those tools is exactly the contributor profile worth optimizing for. The friction self-selects.

> "I'm sorry for everyone who is not that technical, but I think it's the easier way you should learn."
> — daily thought, 2026-05-22

## What happens after merge

The author may run [[ingest]] on a new source you contributed, [[reflect]] on a daily thought, [[edit]] to fold a concept page into the broader wiki structure, or [[lint]] to verify link integrity across the merge. Your PR is the input; the post-merge author flow is the next step. Your name lands in [[CONTRIBUTORS]] either way.

## If your PR is closed

Do not take it personally. The most common reasons:

- The contribution is in scope but the evidence does not support the claim strongly enough to merge.
- The contribution restates an existing wiki frame without new lift.
- The contribution is out of scope and should have been a GitHub issue.
- The voice is off and the rewrite cost exceeds the contribution's value.

The author will leave a one-line reason on the PR. Iterate, or move on.

## Status of this charter

`status: draft`. The charter itself is one of the [[05_open-questions]] resolved in this pass. It will mutate as real contributions accumulate and the actual failure modes become visible. Material revisions are logged in [[log]].

## Related

- [[06_collaboration]] — the full collaboration model. This charter operationalises §T1 of that page.
- [[05_open-questions]] — the live decisions the wiki is still resolving; the scope-check step of [[contribute]] reads this file.
- [[00_initial-brief]] — the research frame the charter enforces.
- [[04_distribution]] — what the finished paper looks like as a product; the charter governs the wiki *in flight*.
- [[01_audience]] — the voice calibration the charter inherits.
- [[CONTRIBUTORS]] — the merged-contributor roll.
