---
title: Collaboration
status: draft
tags:
  - planning
  - collaboration
  - contribution
last-updated: 2026-05-22
---

# Collaboration

How other people contribute to, and consume from, this research while it is still being assembled. Adjacent to [[04_distribution]] (which is about the *finished* artifact) but distinct: collaboration is about the **wiki itself as a living surface**, not the white paper as a product.

## Premise

The wiki is meant to compound. New sources, daily thoughts, and concept refinements should arrive faster than a single author can produce them, while the **voice and the research questions stay coherent**. This page brainstorms ways to invite that flow without breaking coherence.

Two constraints frame everything below:

1. **The audience is operators** — founders, technical entrepreneurs, "smart founders" who use AI in their own work. The contribution surface should match their existing tools (GitHub, LLMs, terminals) rather than ask them to learn a new platform.
2. **Curation is the bottleneck, not authoring.** The author has already accepted (see [[#raw-material-2026-05-22]]) that **every contribution is reviewed before merge**. So the design problem is not "how do we get more contributions" — it is "how do we make each contribution legible and reviewable in minutes, not hours."

## Tiered options — small to big

The five tiers below are additive, not mutually exclusive. Each later tier assumes the earlier one exists.

### T0 — LLM-queryable repo + static site (read-only, baseline)

**What it is:**

Two parallel read surfaces that share a single source of truth (the `wiki/` folder):

#### Surface A — GitHub repository (for technical readers)

The repo ships public with the following root files in place:

```
/
├── CLAUDE.md              ← project instructions; read by any LLM on first open
├── README.md              ← human-readable entry: what this is, how to use it, how to contribute
├── CONTRIBUTING.md        ← contributor charter; links to the /contribute skill
├── raw/                   ← source material (PDFs, screenshots, transcripts, daily thoughts)
│   └── daily tougths/     ← author's voice notes; agent reads but never reorganizes
├── wiki/                  ← processed knowledge layer; agent writes here
│   ├── index.md           ← catalog of every page; always read first
│   ├── log.md             ← append-only operations log
│   ├── 01_paper-planning/ ← brief, audience, structure, distribution, open questions, vocab
│   ├── 02_hypothesis/     ← working hypotheses (H1, H2, H3, ...)
│   ├── 03_search/         ← bibliography and search plan
│   ├── 04_concepts/       ← concept pages (one concept per file)
│   ├── 05_sources/        ← source stubs and syntheses
│   ├── 06_ideas/          ← concrete use-case patterns
│   ├── data/              ← citable data points (one per file)
│   └── thoughts/          ← reflection memory trail
├── outputs/               ← generated HTML lecture pages (one per concept)
└── .claude/
    └── skills/            ← /ingest, /ask, /reflect, /lint, /discover, /edit, /visualize, /contribute
```

Any LLM pointed at this repo (Claude Code, ChatGPT, Cursor, Gemini CLI) can run:
- `"Summarize the U-curve hypothesis"` → reads [[H2_u-curve-of-value]]
- `"What counter-evidence exists against H1?"` → reads [[H1_L0-L7-ladder]]
- `"What open questions still need answering?"` → reads [[05_open-questions]]

This is the canonical surface for contributors.

#### Surface B — Static site (view-only, for non-technical readers)

A static render of `wiki/` — browsable pages with working wikilinks — deployed without any backend. No account required. Read-only.

**Recommended tool: [Quartz](https://quartz.jzhao.dev/)** — designed specifically for Obsidian-flavored Markdown, handles `[[wikilinks]]` natively, produces fast static HTML, free to self-host on GitHub Pages or Cloudflare Pages.

What the static site provides:
- Browse any wiki page in a browser
- Follow wikilinks between pages (no cloning required)
- Search across all pages
- Graph view of page connections (Quartz default)
- Rendered frontmatter: `status`, `confidence`, `tags`, `last-updated` visible at a glance

What it does **not** provide:
- Any way to contribute (contribution is T1 only, via GitHub)
- The `raw/` folder (excluded from the build; it is private source material)
- The `outputs/` HTML lectures (linked from wiki pages but served separately)

**Deployment:** push a GitHub Action that runs `quartz build` on every merge to `main`. The static site auto-updates whenever a PR merges. URL: `wherevaluelands.com` or `wiki.wherevaluelands.com` (domain decision open).

Why:
- This is essentially what [[04_distribution]] already commits to ("LLM-queryable wiki on GitHub"). Collaboration starts here — every later tier assumes T0 exists.
- The repo *is* the manifesto. People who can clone and query the corpus are exactly the audience the paper is trying to reach.
- The static site is the safety valve: people who find the paper through LinkedIn or a newsletter can explore the research without needing a terminal.

Effort: low-medium. Repo structure already exists; Quartz config is a half-day setup; GitHub Action is boilerplate.

### T1 — Pull requests via a `/contribute` skill (canonical contribution path)

**What it is:**

A skill — `/contribute` — sibling to the existing seven ([[#how-it-fits-with-existing-skills]] below).

#### The `/contribute` skill specification

**Entry point:** The contributor forks the repo, opens it in Claude Code (or any agentic CLI), runs `/contribute`.

**Step 1 — Scope check.** Before anything is written, the skill reads [[05_open-questions]] and the first section of [[index.md]] and surfaces the *active research questions* to the contributor. This is the scope filter: if the contributor's idea is outside these questions, the skill says so before any writing happens.

**Step 2 — Contribution kind.** The skill asks:

```
What kind of contribution is this?

  [1] New source       — a paper, article, book, or dataset you think should be ingested
  [2] Daily thought    — your own reflection on the research questions
  [3] Concept note     — a concept that is missing from the wiki or needs expanding
  [4] Open question    — a question or gap you noticed that the wiki does not address
```

**Step 3 — Per-kind workflow:**

| Kind | What the skill does |
|---|---|
| **New source** | Collects: title, URL or file path, why it's relevant, which wiki pages it might touch. Drops a structured stub in `raw/` with enough metadata for the author to run `/ingest` on it post-merge. |
| **Daily thought** | Prompts the contributor to write freely. The skill structures the output into the same format as the author's own daily thoughts (themes, claims, questions). Saves to `raw/daily tougths/` as `YYYY-MM-DD_<contributor-handle>.md`. |
| **Concept note** | Checks [[index.md]] for existing pages on the topic. If the concept exists, opens it for the contributor to read before adding. Produces a well-formed wiki page draft in `wiki/04_concepts/` with correct frontmatter, a clear claim, and at least two wikilinks to existing pages. |
| **Open question** | Drafts a single clean question with a one-line rationale and proposes a place in [[05_open-questions]] under an appropriate section heading. |

**Step 4 — Branch + PR description.** The skill creates a new branch (`contrib/<handle>/<topic>`) and prepares a PR description template:

```markdown
## What this adds
<1–3 sentences>

## Why it matters to the research
<which open question or hypothesis does this touch, and how>

## Pages affected
- [[page-a]]: <how>
- [[page-b]]: <how>

## Claim or question it sharpens or challenges
<one sentence>
```

The author should be able to accept or reject in <5 minutes by reading the PR description, not by re-reading the diff.

**Step 5 — Forward → reverse link check.** Before the PR is opened, the skill checks that any new wikilinks added by the contribution have the corresponding reverse link on the target page. If missing, it flags them.

**Why it works:**
- **Aligns with the project's git-native, LLM-wiki ethos.** No new platform.
- **Self-selection.** A founder who can run a CLI and open a PR is exactly the contributor profile worth optimizing for. The friction is a quality filter, not a bug.

**Why it is *not enough on its own*:**
- Excludes non-technical operators (already acknowledged: "I'm sorry for everyone who is not that technical").
- Surface is invisible: people only contribute if they already know the repo exists.

Effort: medium. Mostly a SKILL.md authoring exercise plus a `CONTRIBUTING.md` at the repo root.

### T2 — Auto digest / newsletter (lightweight broadcast back)

What it is:

- A scheduled job (GitHub Action, weekly) reads `wiki/log.md` for new entries since the last digest, summarizes them into a short newsletter (3–6 bullets: what was ingested, what concepts emerged, what the open questions look like now).
- Delivered via Buttondown / Substack / a single Mailgun route — whatever requires the least platform commitment.
- Subscribers can **reply** to the email. Replies that contain a URL or a source are auto-filed as candidate PRs in a `proposals/` folder for the author to triage.

Why:

- Closes the loop. T1 contributors get nothing back today; the digest gives them a sense of the wiki's momentum and surfaces other people's contributions.
- **Asymmetric leverage:** zero ongoing authoring cost — the digest is generated from the log — but a real distribution surface.
- Subscriber reply → candidate PR is a way to accept low-friction contributions from non-technical readers without lowering the merge bar.

Risks:

- Email subscribers may become passive readers, not contributors. Accept this — converting 5% of subscribers into PR authors is a win.

Effort: low-medium. One Action workflow + a transactional email account.

### T3 — Community surface (LinkedIn / X / Discord, synced to the wiki)

What it is:

Pick **one** community channel and treat it as a downstream read-replica of the wiki, not a separate forum:

- **Option 3a: LinkedIn page** — most natural for the founder/operator audience. Every wiki concept reaching `status: stable` or every hypothesis whose confidence ticks up auto-drafts a LinkedIn post for the author to edit and ship. Comments on the post are a candidate-source firehose.
- **Option 3b: X/Twitter account** — auto-posts log entries with the wikilink resolved to the static-site URL from T0. Better for technical reach, worse for the European operator audience the paper targets.
- **Option 3c: Discord / Slack contributor space** — invite-only, sized small (~30–50 contributors), threaded around specific hypothesis pages. **Highest signal, highest moderation cost.**

Recommendation: **3a first, 3c later** if the contributor pool grows beyond what async PR review can handle. Skip 3b unless the project takes an explicit US-technical-reach turn.

Why this is gated, not free:

- A community channel that runs *ahead of* the wiki dilutes the voice. Treat it as a **broadcast surface that points back into the repo**, not a discussion forum that produces parallel content.
- One channel max. Two channels = three communities (the two channels + the people on neither), each demanding maintenance.

Effort: medium. Mostly about writing discipline, not engineering.

### T4 — Web application: chat-with-the-wiki

What it is:

A small web app at, say, `wherevaluelands.com` that hosts:

- A **public LLM frontend** over the corpus (Claude or open-weight model, RAG-indexed on the wiki). Anyone can ask the wiki questions without cloning the repo.
- An **invited-write tier** for vetted contributors — a small "smart founders" list. They get an account, can write daily thoughts directly through the app, and the app opens a PR on their behalf. Author still reviews.
- A **citation surface**: every answer the LLM gives links back to the specific wiki pages, so the app drives traffic into the repo, not away from it.

Why this is the biggest bet:

- Lowest friction for non-technical contributors — they get a chat box, the agent does the wiki-shape conversion.
- Reframes the project from "research output" to "shared research instrument." Aligned with the daily thought's closing line: *"a tool to all these successful founders to easily share experiences just by prompting and collaborate with others and see how their thoughts are shaped by the others."*
- Lets the project survive past the white paper. The paper is the v1 deliverable; the app is the v2 vehicle.

Why this is risky:

- Engineering cost is meaningfully higher than everything above.
- Once an app exists, expectations rise — uptime, account management, abuse, moderation.
- The wiki's coherence depends on the author's voice. A "chat box for founders" can flood the curation queue with low-quality material faster than any other tier.

Effort: high. Probably a separate sub-project with its own spec.

## Recommended sequence

Ship now (cost = days):

1. **T0** — publish the repo public, add `CONTRIBUTING.md`, confirm `CLAUDE.md` is LLM-friendly.
2. **T1** — write the `/contribute` skill.

Ship in 4–6 weeks, around the paper release ([[04_distribution]] timing):

3. **T2** — auto-digest from `wiki/log.md`. Use the white paper launch to seed the subscriber list.

Ship in 2–3 months, only if the previous tiers produce signal:

4. **T3a** — LinkedIn page synced to the log. Skip if the digest already saturates the audience.

Defer indefinitely, revisit after paper publication:

5. **T4** — only if there is a concrete second-project thesis ("the wiki is the v2 vehicle"). Otherwise the engineering cost is not justified by paper-launch goals alone.

The principle: **don't ship a tier whose curation cost exceeds the previous tier's contribution volume.** If T1 produces three PRs a month, do not also stand up a Discord.

## Risks

- **Curation bottleneck.** The author is the single merge gatekeeper. PR backlog is the natural failure mode. Mitigation: a hard rule that any PR > 7 days unreviewed gets closed with a note, not silently aged.
- **Voice dilution.** The wiki's value is the coherence of one author's reading of the field. Every additional contributor is a small dilution. Tolerable up to a point; the merge bar is the only enforcement mechanism. **Reject more than you accept, especially early.**
- **Scope creep.** Contributors will propose extensions to questions the paper does not intend to answer (e.g. consumer AI, robotics — see [[05_open-questions]]). The `/contribute` skill should make the scope visible — show the contributor the active research questions before they start writing — so off-topic PRs are filtered at authoring time, not at review time.
- **Platform commitment ratchet.** Every new community surface (mailing list, LinkedIn page, Discord) is a forever-commitment to the audience that uses it. Tier 3 onward is harder to retreat from than to enter. Adopt slowly.

## How it fits with existing skills

`/contribute` is the new sibling. It does **not** replace the existing skills — it is the contributor-side counterpart:

| Skill | Maintainer-side | Contributor-side |
|---|---|---|
| `/ingest` | Author folds a source into the wiki | `/contribute` walks a contributor through dropping a source into `raw/` on a fork, with a PR description that mimics what `/ingest` would produce |
| `/reflect` | Author dialogues with their own daily thought | `/contribute` lets a contributor add their own daily thought, with the understanding that the author's `/reflect` may engage with it post-merge |
| `/edit` | Author makes structural changes | Out of scope for contributors. Structural edits are author-only. |
| `/ask`, `/lint`, `/discover`, `/visualize` | Author-side only | Out of scope. |

Design rule: `/contribute` produces output the author can run `/ingest` or `/reflect` against after merge. It is a **PR-shaped wrapper around the same primitives**, not a parallel writing path.

## Open decisions

Promoted to [[05_open-questions]]:

- [ ] **Repo license** — already listed there; collaboration tier choices depend on it. MIT and CC-BY are friendly to T1–T4. CC-BY-NC complicates T4 (the app) substantially.
- [ ] **`/contribute` skill scope** — should it support all four contribution kinds (source, daily thought, concept extension, open question) at v1, or ship narrow (source + daily thought only) and extend?
- [ ] **Newsletter platform** — Buttondown vs. Substack vs. self-hosted Mailgun route. Decision driven by whether the digest is a *list* (Buttondown) or a *publication* (Substack).
- [ ] **Contributor charter** — explicit one-page document on what counts as a good contribution, linked from `CONTRIBUTING.md`. Probably required before T1 ships publicly.

## Related

- [[04_distribution]] — channels and timing for the *finished* paper; collaboration here is about the wiki *in flight*.
- [[05_open-questions]] — decisions blocking specific tiers above.
- [[00_initial-brief]] — the frame the contributor charter has to enforce.
- [[07_analytical-vocabulary]] — vocabulary reference; the `/contribute` skill scope-check step reads [[05_open-questions]], whose vocabulary now follows this page.
- [[08_contributor-charter]] — the high-bar standard for what counts as a good contribution; operationalises §T1 of this page.

## Discussed in
- [[archetypes-vocabulary-personal-frame]]

## Raw material — 2026-05-22

This page was opened from the daily thought of 2026-05-22, in which the author articulated:

- The wiki is an **LLM Wiki, open in development**.
- Contribution path: fork → `/contribute` → PR → author reviews → merge or reject.
- Acceptable friction: contributors should be technical enough to use a CLI. *"I'm sorry for everyone who is not that technical, but I think it's the easier way you should learn."*
- Long-term goal: *"a tool to all these successful founders to easily share experiences just by prompting and collaborate with others."* — this is the T4 thesis.
