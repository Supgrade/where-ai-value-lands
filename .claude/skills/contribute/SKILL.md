---
name: contribute
description: This skill should be used when the user is a fork-author who wants to contribute back to the wiki, or asks to "contribute", "open a contribution PR", "submit a source", "add a daily thought", "propose a concept page", "open a question for the wiki", or otherwise refers to producing a pull request against the canonical repository. Walks the contributor through a scope check against active research questions, picks the contribution kind, drafts the file in the correct location with correct frontmatter, runs a forward → reverse link check, and produces a PR description the author can review in minutes. Does not push or open the PR — the contributor runs the final `gh` command.
---

# Contribute

Turns an external contributor's idea into a clean, reviewable PR against the canonical wiki. This is the contributor-side counterpart to [[ingest]] and [[reflect]] — it produces output the author can run those skills against after merge.

The skill optimises for the author's review time, not the contributor's writing time. A well-formed PR is one the author can accept or close in under five minutes by reading the PR description, without re-reading the diff. Most PRs are closed. This is intentional — see [[08_contributor-charter]].

---

## Stance

This is an open inquiry, not a defense of pre-baked frameworks. Contributors are encouraged to introduce evidence that complicates or contradicts existing hypothesis pages ([[H1_L0-L7-ladder]], [[H2_u-curve-of-value]]) — but contradictions must be flagged explicitly in the PR description, not buried in the diff.

---

## Pre-flight check

Before doing anything, verify the operating environment.

1. **Confirm this is a fork**, not the canonical repository. The canonical repo is `github.com/Supgrade/where-AI-value-lands`. Run:
   ```bash
   git remote -v
   ```
   If the only remote is `Supgrade/where-AI-value-lands`, refuse and tell the contributor to fork first. The author does not accept PRs from a clone of the canonical repo.

2. **Confirm the current branch is `main`** (or `master`):
   ```bash
   git branch --show-current
   ```
   If on another branch, ask the contributor whether they want to start a fresh branch from `main` (recommended) or extend the current one.

3. **Confirm `gh` is installed and authenticated**:
   ```bash
   gh auth status
   ```
   If not authenticated, the contributor will not be able to open the PR at the end. Continue anyway; the skill will print the `gh pr create` command and the contributor can authenticate before running it.

If any check fails in a way that blocks the work, surface the problem in one short sentence and let the contributor decide whether to continue.

---

## Step 1 — Scope check

Before any writing, surface the project's active research questions to the contributor and let them decide whether their idea is in scope.

Read:

1. `wiki/01_paper-planning/05_open-questions.md` in full.
2. The first 50 lines of `wiki/index.md`.
3. `wiki/01_paper-planning/00_initial-brief.md` (short — read in full).

Summarise back to the contributor, in a short numbered list:

- The working title and the question the paper is asking (one line, from the brief).
- The three working hypotheses with their current confidence (one line each).
- The active open questions, grouped: research-blocking, drafting-blocking, publishing-blocking.
- The explicit out-of-scope list from the brief / open questions: embodied AI and robotics, consumer AI, ML research, general AI safety.

Then ask, in one sentence:

> _"Does what you want to contribute touch one of these questions or hypotheses, or is it orthogonal? If orthogonal, the PR is likely to be closed — see [[08_contributor-charter]]."_

If the contributor signals orthogonal-but-proceed-anyway, note that in your eventual PR description so the author can close it quickly without re-reading the diff. Do not refuse the contribution — the contributor's time is theirs to spend.

---

## Step 2 — Contribution kind

Ask, exactly as below:

```
What kind of contribution is this?

  [1] New source       — a paper, article, book, or dataset you think should be ingested
  [2] Daily thought    — your own reflection on the research questions, from inside the operator role
  [3] Concept note     — a concept that is missing from the wiki or needs expanding
  [4] Open question    — a question or gap you noticed that the wiki does not address
```

Wait for the choice before continuing. The four kinds use different workflows.

---

## Step 3 — Per-kind workflow

### Kind 1 — New source

The contribution is a stub the author will later turn into a full source page via [[ingest]] post-merge.

**Collect from the contributor:**

- Title, author(s), year, venue (journal, publisher, blog, podcast, conference).
- URL or local file path. If they have the file, ask them to drop it into `raw/` themselves and tell you the filename.
- One-paragraph reason it bears on the research — which hypothesis or open question does it touch, and how.
- Two or three wiki pages it would most likely interact with (check `wiki/index.md` for accurate slugs).
- Whether it is a primary source or a secondary synthesis. Flag if the latter.

**Where the file lands:**

`raw/<descriptive-slug>.md` if it is a stub, or `raw/<filename>.<ext>` if the contributor uploaded the original. Use lowercase-hyphenated slugs.

For a stub, the structure is:

```markdown
# <Source Title>

**Author(s):** <names>
**Year:** <YYYY>
**Venue:** <where it was published>
**URL:** <link, or "local file: raw/<filename>">
**Primary or secondary:** <primary | secondary synthesis>

## Why this matters to the research

<one paragraph — which hypothesis or open question does this touch>

## Wiki pages likely affected

- [[<slug>]] — <one line on how>
- [[<slug>]] — <one line on how>

## Suggested by

<contributor handle> — <date>
```

**What happens post-merge:** the author runs [[ingest]] on the file. The stub is consumed; the resulting source page lives in `wiki/05_sources/` and the file moves to `raw/ingested/`.

---

### Kind 2 — Daily thought

The contribution is a contributor's own stream-of-consciousness reasoning about the research questions, written from inside the operator role. The author may engage with it via [[reflect]] post-merge — selective promotion, not automatic ingestion. Most of what the contributor writes stays as is; only a fraction earns a place in the wiki.

**Collect from the contributor:**

- Their handle (short, lowercase, no spaces — used in the filename).
- A free-form draft of the thought. Do not impose structure during writing; the structuring happens after.

Once the draft is in, restructure it into the same shape as the author's existing daily thoughts:

- One-sentence framing of what the thought is about.
- The threads or sub-claims the thought touches (numbered or bulleted).
- For each thread, the relevant wiki pages (check `wiki/index.md` and skim 2–4 candidate pages before linking).
- An optional "what I am not sure about" block at the end.

**Where the file lands:**

`raw/daily tougths/YYYY-MM-DD_<contributor-handle>.md`

(Note the existing folder name is `daily tougths` — the typo is preserved deliberately. Do not rename.)

**Frontmatter:**

```yaml
---
title: <one-line framing>
date: YYYY-MM-DD
contributor: <handle>
tags:
  - daily-thought
  - contribution
---
```

**What happens post-merge:** the author may run [[reflect]] against the file. The original is preserved verbatim; an annotated companion may be written next to it (`YYYY-MM-DD_<handle> annotated.md`), and a brief memory marker may land in `wiki/thoughts/`. The contributor's name is preserved in the filename and in git history.

---

### Kind 3 — Concept note

The contribution is a new concept page, or a substantive extension of an existing one.

**First, check for duplicates.** Read `wiki/index.md` and look for any existing concept page with a similar slug or topic. If one exists:

- Open it with the contributor and ask: is your contribution a refinement of this existing page, or a genuinely new concept?
- If refinement: do not create a new file. Instead, prepare a patch — describe the addition in the PR description and the contributor edits the existing page in their fork. The PR diff is the change.
- If new concept: confirm the proposed slug does not collide with anything in the index.

**Collect from the contributor:**

- The concept's name and proposed slug (lowercase, hyphen-separated).
- A clear one-line claim: what does this concept name? What handle does it give to a recurring idea in the field?
- At least two existing wiki pages the new concept connects to.
- At least one source citation (wikilink to an existing source page, or a stub for a new source dropped in `raw/`).
- Whether the concept supports, complicates, or contradicts any existing hypothesis. Be explicit.

**Where the file lands:**

`wiki/04_concepts/<slug>.md`

**Required structure:**

```markdown
---
title: <Concept Name>
status: draft
tags:
  - concept
  - <topic-tag>
  - <topic-tag>
last-updated: YYYY-MM-DD
contributors: <handle>
---

# <Concept Name>

<one-paragraph claim — what this concept names and why it matters>

## What it is

<2–4 short paragraphs developing the claim>

## Evidence

- <claim with wikilink to source>
- <claim with wikilink to source>

## Tensions

<how this concept supports, complicates, or contradicts existing hypotheses — be explicit; flag the hypothesis page by wikilink>

## Open questions

- <question 1>
- <question 2>

## Related

- [[<slug>]] — <one line>
- [[<slug>]] — <one line>
```

Keep body under 400 words. Split into a sibling page if it grows larger.

**What happens post-merge:** the author may run [[edit]] to fold the new concept into the broader wiki structure, [[lint]] to verify reverse-link integrity, or [[ask]] to test how the new concept interacts with adjacent material.

---

### Kind 4 — Open question

The contribution sharpens or adds a question the wiki should be asking but currently is not.

**Collect from the contributor:**

- The question itself, in one clean sentence.
- A one-line rationale: why does this need answering? What downstream decision does the answer block?
- Which section of `wiki/01_paper-planning/05_open-questions.md` it belongs under. Read the file with the contributor and pick the right section together. The current sections are:
  - Before research starts in earnest
  - Before drafting scenarios
  - Before publishing
  - Possibly out of scope
  - Collaboration model
  - Analytical vocabulary
  - Business archetype taxonomy
- Optionally, a "sharpened by" link to a source or concept page that motivated the question.

**Where the change lands:**

The contributor edits `wiki/01_paper-planning/05_open-questions.md` in their fork — they do not create a new file. The edit is small and reviewable.

**Format for the new line:**

```markdown
- [ ] **<short question handle>** — <full question in one sentence>. <one-line rationale>.
  - **Sharpened by** [[<slug>]]: <one line on the connection>. (optional)
```

**What happens post-merge:** the question becomes part of the live open-questions list. The scope-check step of this skill will surface it to future contributors on its next run.

---

## Step 4 — Branch + PR description

Create a branch:

```bash
git checkout -b contrib/<handle>/<topic-slug>
```

Where `<handle>` is the contributor's GitHub username and `<topic-slug>` is a short kebab-case description of the contribution.

Stage and commit:

```bash
git add <files>
git commit -m "<one-line summary>"
```

Prepare the PR description in a temp file (or in memory). Use this template verbatim:

```markdown
## What this adds

<1–3 sentences>

## Kind

<New source | Daily thought | Concept note | Open question>

## Why it matters to the research

<which open question or hypothesis does this touch, and how>

## Pages affected

- [[page-a]]: <how>
- [[page-b]]: <how>

## Page links

<GitHub does not render Obsidian wikilinks. Repeat the page list above as relative file links so reviewers can click through.>

- [page-a](wiki/04_concepts/page-a.md): <how>
- [page-b](wiki/04_concepts/page-b.md): <how>

## Claim or question it sharpens or challenges

<one sentence — name the hypothesis or open question, and say whether this supports, complicates, or contradicts it>

## Scope check

<"In scope" if it touches an active research question; "Orthogonal but submitted anyway" otherwise — be honest, do not hide an out-of-scope contribution>

## Notes for the maintainer

<anything the author should know before reviewing — e.g. "this is a secondary synthesis, not a primary source"; "the daily thought is in Italian-influenced English, untouched">
```

The author must be able to accept or close the PR in under five minutes by reading the description — without re-reading the diff. If the description does not state which open question or hypothesis the contribution touches, the PR will be closed without review.

---

## Step 5 — Forward → reverse link check

Before opening the PR, audit the wikilinks the contribution introduced.

For each new wikilink `[[X]]` added on page A:

1. Resolve `X` to a file path. Search `wiki/` for `<X>.md`.
2. Read the target file's body and check whether page A is referenced anywhere — either as a wikilink `[[A]]` or under a "Related", "See also", or "Linked from" section.
3. If page A is not referenced on the target, flag it:
   - **If the target is a page the contribution itself created (Kind 3),** add the reverse link to the target's "Related" section as part of this same PR.
   - **If the target is an existing wiki page,** do **not** silently edit existing wiki pages. Instead, surface the missing reverse link to the contributor with a clear choice:
     - (a) Add `[[A]]` to the target page's "Related" section as part of this PR (recommended — small, low-risk edit).
     - (b) Leave it; the author will add the reverse link during merge.
   - Note the chosen path in the PR description's "Notes for the maintainer" section.

The rationale is in [[CLAUDE]]: forward → reverse link rule is enforced in the same pass, not deferred. Following it during contribution time keeps the wiki link graph clean as it scales.

---

## Step 6 — Open the PR

Do **not** push or open the PR yourself. The contributor runs the final commands. Print the exact commands for them to copy:

```bash
git push -u origin contrib/<handle>/<topic-slug>

gh pr create \
  --repo Supgrade/where-AI-value-lands \
  --base main \
  --head <contributor-fork-owner>:contrib/<handle>/<topic-slug> \
  --title "<one-line summary>" \
  --body-file <path-to-pr-description-file>
```

Alternative without `gh`: print the GitHub web URL for opening a PR:

```
https://github.com/Supgrade/where-AI-value-lands/compare/main...<contributor-fork-owner>:<fork-repo-name>:contrib/<handle>/<topic-slug>?expand=1
```

The contributor authenticates, runs the commands, and the PR appears. Tell the contributor what to expect next — see "After the PR is open" below.

---

## After the PR is open

The author will:

1. Read the PR description (the only thing the merge bar judges).
2. Skim the diff to confirm it matches the description.
3. Either merge or close. Most PRs are closed. See [[08_contributor-charter]] for the merge bar.
4. On merge: add the contributor's name to [[CONTRIBUTORS]] if it is their first merge; potentially run [[ingest]] (Kind 1), [[reflect]] (Kind 2), [[edit]] (Kind 3), or [[lint]] (any kind) as a follow-up.

If the PR is closed, the author will leave a one-line reason. Do not take it personally — iterate or move on.

---

## Out of scope

This skill will not:

- Push to a remote. The contributor pushes.
- Open the PR via the GitHub API. The contributor runs `gh` or uses the web UI.
- Run [[ingest]], [[reflect]], [[edit]], [[lint]], [[discover]], [[visualize]], or [[ask]]. Those are author-side operations.
- Make structural changes — renames, splits, merges, page deletions. Those are author-only via [[edit]]. If a contributor wants a structural change, the right path is a GitHub issue, not a PR.
- Modify existing wiki pages directly, except:
  - Adding a reverse link to a target page's "Related" section (Step 5, option (a)).
  - Adding one line to `wiki/01_paper-planning/05_open-questions.md` (Kind 4).
  - Editing an existing concept page when the contributor explicitly chose "refinement of existing page" in Kind 3.
- Touch `wiki/index.md`, `wiki/log.md`, or any hypothesis page in `wiki/02_hypothesis/`. Those are author-only.

---

## What not to do

- Do not write the PR description for the contributor without their input. The skill structures and prompts; the contributor supplies the substance.
- Do not skip the scope-check step (Step 1). It is the most important step. A PR that fails scope-check costs the author time the contributor could have saved.
- Do not invent wikilink slugs. Verify each slug exists in `wiki/index.md` or in the files the contribution itself creates.
- Do not auto-add the contributor's name to [[CONTRIBUTORS]]. The author does that on merge.
- Do not produce summaries of existing wiki pages as "concept contributions." Restating an existing frame without new lift is the most common reason for closure.
- Do not soften the merge bar in conversation. The friction is the feature; tell the contributor honestly that most PRs are closed.

---

## Related

- [[06_collaboration]] — the full collaboration model, including the tiers above and below T1.
- [[08_contributor-charter]] — the merge bar this skill enforces at contribution time.
- [[CLAUDE]] — project conventions (slugs, frontmatter, forward → reverse link rule).
- [[ingest]] — author-side counterpart that consumes the output of a Kind 1 contribution.
- [[reflect]] — author-side counterpart that engages with a Kind 2 contribution.
- [[edit]] — author-side counterpart for structural changes the skill explicitly does not perform.
