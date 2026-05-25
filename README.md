# Where Value Lands in the Age of Agentic AI

An open inquiry into where economic value lands across the agentic AI stack over the next 2–5 years, with a 5–10 year horizon. Built as a secondary-research white paper and published with its full research corpus as an LLM-queryable wiki.

The paper is the visible tip. This repository is the iceberg.

## Stance

This is an open inquiry, not a defense of pre-baked frameworks. The working hypotheses in [`wiki/02_hypothesis/`](wiki/02_hypothesis/) — the L0–L7 stack ladder, the U-curve of value, the orthogonal-axes claim — are starting scaffolding, not conclusions. They mutate, merge, or retire as evidence comes in. Each carries an explicit `Status`, `Confidence`, and `What would retire this` block.

## Audience

Operators who own meaningful assets — proprietary data, distribution, capital, infrastructure — but lack a deep technical model of where AI is heading. Founders, VCs, CEOs, senior technical operators. Peer-to-peer voice. No hype, no hedging. Strong claims carry citations or are labeled as bets.

If you can clone a repo and point an LLM at a folder, the corpus is yours to query.

## How to read this

Three entry points, in order of depth:

1. **The static site** (browser, view-only) — `https://supgrade.github.io/where-ai-value-lands/` once deployed. Quartz-rendered wiki with working wikilinks, search, and a graph view. No clone required.
2. **The wiki itself** — open `wiki/index.md`. Every page in the wiki is listed there with a one-line summary, organized by category. Follow `[[wikilinks]]` from there.
3. **Query with your own LLM** — clone the repo, point Claude Code, Cursor, ChatGPT, or any agentic CLI at the root. The file [`CLAUDE.md`](CLAUDE.md) is read first by any LLM that opens the project; it sets the conventions and stance.

Sample queries that work out of the box:

- *"Summarize the U-curve hypothesis and the strongest counter-evidence against it."*
- *"What does the wiki say about middle-layer defensibility?"*
- *"What are the active open questions for the paper?"*
- *"Which sources support the bear case, and where do they disagree with each other?"*

## Structure

```
/
├── CLAUDE.md              ← project instructions; read by any LLM on first open
├── README.md              ← you are here
├── CONTRIBUTING.md        ← contribution path; pointer into the charter
├── CONTRIBUTORS.md        ← roll of merged contributors
├── LICENSE                ← MIT (code)
├── LICENSE-content        ← CC BY 4.0 (wiki content)
├── raw/                   ← source material (PDFs, screenshots, transcripts, daily thoughts)
│   └── daily tougths/     ← author's voice notes; agent reads but never reorganizes
├── wiki/                  ← processed knowledge; agent writes here
│   ├── index.md           ← catalog of every page; always read first
│   ├── log.md             ← append-only operations log
│   ├── 01_paper-planning/ ← brief, audience, structure, distribution, open questions
│   ├── 02_hypothesis/     ← working hypotheses (H1, H2, H3, ...)
│   ├── 03_search/         ← bibliography and search plan
│   ├── 04_concepts/       ← concept pages (one concept per file)
│   ├── 05_sources/        ← source stubs and syntheses
│   ├── 06_ideas/          ← concrete use-case patterns
│   ├── data/              ← citable data points (one per file)
│   └── thoughts/          ← reflection memory trail
├── outputs/               ← generated HTML lecture pages, one per concept
└── .claude/
    └── skills/            ← the agentic skills that run the wiki
```

Two layers, two principles:

- **`raw/`** is the user's dump zone. Flat. Read-only to the agent, with the single exception that the agent may write an annotated companion next to a daily-thought note when running `/reflect`.
- **`wiki/`** is the processed knowledge layer. The agent owns it. New sources flow in via `/ingest`, new concepts via `/edit`, new contributions via `/contribute`.

See [`CLAUDE.md`](CLAUDE.md) for the full conventions: slug format, wikilinks, the forward → reverse link rule, hypothesis-page blocks, frontmatter shape.

## Skills

Eight skills run the wiki. They live in `.claude/skills/<name>/SKILL.md`.

| Skill                                                                     | What it does                                                                                                                     |
| ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| [`ingest`](.claude/skills/inge[[.claude/skills/ingest/SKILL]]st/SKILL.md) | Fold a new source from `raw/` into the wiki. Creates and updates pages, maintains wikilinks both directions, appends to the log. |
| [`ask`](.claude/skills/ask/SKILL.md)                                      | Answer a question against the wiki. Optionally crystallize the answer back as a new page.                                        |
| [`reflect`](.claude/skills/reflect/SKILL.md)                              | Engage with a daily-thought note as a dialogue. Selectively promote durable material into the wiki.                              |
| [`visualize`](.claude/skills/visualize/SKILL.md)                          | Generate a self-contained HTML lecture page for one concept, with an interactive graph of its connections.                       |
| [`lint`](.claude/skills/lint/SKILL.md)                                    | Health check. Flags broken links, orphans, missing reverse links, stale confidence claims.                                       |
| [`discover`](.claude/skills/discover/SKILL.md)                            | Propose a ranked shortlist of candidate sources from wiki gaps and recent online discourse.                                      |
| [`edit`](.claude/skills/edit/SKILL.md)                                    | Structured renames, splits, merges, deletions. Preserves link integrity.                                                         |
| [`contribute`](.claude/skills/contribute/SKILL.md)                        | Walk a fork-author through producing a clean PR back to the wiki. Contributor-side counterpart to `/ingest` and `/reflect`.      |

The first seven are author-side. The eighth, `/contribute`, is the contributor-side wrapper — it produces output that `/ingest` or `/reflect` can run against after merge.

## Status

Working draft. The paper has a 4–6 week target from kickoff to first full draft. Hypotheses still mutating; see [`wiki/02_hypothesis/`](wiki/02_hypothesis/) for current confidence levels and what would retire each. Progress notes are in [`progress.md`](progress.md).

## Contributing

Contributions are technical-by-default — fork, run `/contribute` in an agentic CLI, open a PR. The author is the single merge gatekeeper and rejects more than accepts. See [`CONTRIBUTING.md`](CONTRIBUTING.md) and [`wiki/01_paper-planning/08_contributor-charter.md`](wiki/01_paper-planning/08_contributor-charter.md) before opening anything.

## License

Code (everything under `.claude/skills/` and any future application code): MIT. See [`LICENSE`](LICENSE).

Content (everything under `wiki/`, `raw/`, `outputs/`): CC BY 4.0. See [`LICENSE-content`](LICENSE-content).

By contributing, you agree your contribution is dual-licensed under MIT (for code) and CC BY 4.0 (for content), as applicable.

## Authorship

Gabriele Dalla Costa, primary author and maintainer. The byline / brand wrapper question (personal vs. collective vs. Redacy) is open — see [`wiki/01_paper-planning/05_open-questions.md`](wiki/01_paper-planning/05_open-questions.md).
