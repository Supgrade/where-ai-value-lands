---
name: discover
description: This skill should be used when the user asks to "discover sources", "what should I read next", "find new sources on X", "find recent news on X", "what's been published lately on X", "find related work", or wants a shortlist of candidate sources — drawn from gaps in the current wiki state and from recent online discourse — that could be folded into the wiki via `/ingest`. Proposes a ranked shortlist with one-line justifications. Does not ingest.
---

# Discover

Proposes new sources to read. Two modes, run together:

- **Wiki-driven** — read the current wiki, find gaps (under-evidenced hypotheses, concept pages with thin support, open questions in `wiki/01_paper-planning/05_open-questions.md`), and suggest sources that would fill them.
- **News-driven** — query the open web for recent writing, reports, podcasts, and discourse touching the inquiry's themes (value capture, commodification, where value lands in tech / platforms / labour / capital). Includes academic preprints and serious journalism, not just headlines.

The two modes complement each other: wiki-driven keeps the inquiry rigorous; news-driven keeps it alive.

## Workflow

### 1. Read the wiki state

Read `wiki/index.md`. Read the most recent ~10 entries of `wiki/log.md`. Read `wiki/01_paper-planning/05_open-questions.md`. Skim hypothesis pages' `What would retire this` blocks — those are exactly the kinds of evidence to hunt for.

### 2. Identify gaps

From step 1, produce a working list of:
- Concepts with thin or one-sided evidence.
- Hypotheses where the user would benefit from a steelman of the opposing view.
- Open questions still unanswered.
- Authors or schools referenced but not yet read.

### 3. Web search

Use WebSearch to query for each gap. Compose queries thoughtfully — the agent decides what to search. Useful query shapes:
- Academic: site:arxiv.org, site:ssrn.com, Google Scholar phrasings.
- Critical journalism: long-form magazines, FT, Economist, Bloomberg, The Atlantic, n+1, Logic, Real Life, Phenomenal World.
- Books / reports: think tanks, university presses, recent monographs.
- Recent news: scope to last 12–18 months for currency.

For each candidate, capture: title, author(s), venue, year, URL, a one-sentence claim, and how it relates to the gap.

### 4. Rank

Rank candidates by likely contribution to the inquiry. Heuristics:
- Sources that would directly answer an open question rank higher than tangentially related ones.
- Sources that challenge a current hypothesis rank higher than ones that confirm it (the inquiry is open; disconfirming evidence is more valuable than supporting evidence in expectation).
- Primary sources rank higher than commentary, except when the commentary is itself influential.
- Recent sources rank higher only when recency matters for the claim.

### 5. Produce the shortlist

Output a markdown table or list. Each entry:

```markdown
1. **Title** — Author(s), Venue, Year. [URL]
   - Why it matters: one sentence tying it to a specific gap or hypothesis.
   - Suggested target: [[page-it-would-touch]]
   - Mode: wiki-driven | news-driven
```

Aim for 5–12 candidates per run. More than that is noise.

### 6. Stop

Do not ingest. The user picks from the shortlist and runs `/ingest` on chosen items. If the user wants the agent to fetch URLs into `raw/`, ask first — `raw/` is the user's dump zone.

### 7. Append to the log

```markdown
## [YYYY-MM-DD] discover | scope
- Mode: wiki-driven | news-driven | both
- Candidates surfaced: N
- Gaps targeted: [[concept-a]], [[open-question-b]]
```

## What not to do

- Do not fetch full articles into `raw/` without the user's confirmation per candidate.
- Do not propose sources the wiki already contains. Read the index first.
- Do not rank purely by recency — currency is one signal among several.
- Do not propose 30+ candidates. A long list is the same as no list.
- Do not silently bias toward confirming the U-curve or L0–L7 ladder. Disconfirming sources are valuable.
