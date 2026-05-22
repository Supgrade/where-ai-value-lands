# Contributing

This wiki is meant to compound. New sources, daily thoughts, and concept refinements should arrive faster than a single author can produce them — while voice and research questions stay coherent. Contributions are how that happens.

Most PRs are closed, not merged. This is intentional. Coherence beats volume. The merge bar is high so the wiki stays load-bearing for the paper it supports.

Before opening a PR, read the full [contributor charter](wiki/01_paper-planning/08_contributor-charter.md). It defines what counts.

## The path

1. **Fork** this repository.
2. **Open it in an agentic CLI** (Claude Code, Cursor, Gemini CLI, or any LLM that can read the file tree). `CLAUDE.md` at the root sets the project conventions on first read.
3. **Run `/contribute`.** The skill walks you through scope-checking your idea against the current open questions, choosing the contribution kind, drafting the file in the right place with the right frontmatter, and producing a PR description the author can review in minutes.
4. **Open the PR.** The skill prints the exact `gh pr create` command. You run it.
5. **Wait for review.** The author merges or closes. Closed is normal.

The four contribution kinds the `/contribute` skill supports:

- **New source** — a paper, article, book, or dataset that should be ingested. You drop a structured stub in `raw/` with metadata; the author runs `/ingest` post-merge.
- **Daily thought** — your own reflection on the research questions, written as a contributor of operator perspective. Lands in `raw/daily tougths/` as `YYYY-MM-DD_<your-handle>.md`.
- **Concept note** — a concept missing from the wiki or in need of extension. Drafts a well-formed page in `wiki/04_concepts/`.
- **Open question** — a sharpened question or gap. Proposes an addition to `wiki/01_paper-planning/05_open-questions.md`.

See [`.claude/skills/contribute/SKILL.md`](.claude/skills/contribute/SKILL.md) for the full specification.

## Out of scope

The paper is operator-facing and tightly bounded. The wiki inherits that scope. The following topics are explicitly out of scope unless they directly bear on where AI value lands for capital-rich operators:

- Embodied AI and robotics
- Consumer AI and chat assistants (insofar as they drive frontier-lab economics, ingest as evidence of the substrate layer; do not treat as a primary subject)
- ML research and novel technical contributions
- General AI safety and alignment debates

If you are not sure, open a GitHub issue first and ask before you spend time on a PR.

## What the bar is

The full bar is in the [contributor charter](wiki/01_paper-planning/08_contributor-charter.md). In short:

- Claims have sources. Quantitative claims have data pages.
- Secondary syntheses are flagged as such.
- Bear and bull frames are both engaged.
- The forward → reverse link rule is enforced in the same pass.
- Voice is English, present tense, precise. No marketing language. No hype. No emoji.

If a PR description does not state which open question or hypothesis the contribution touches, it will be closed without further review.

## License

By opening a pull request, you agree that your contribution is dual-licensed:

- Code (anything under `.claude/skills/` or in build / workflow files): **MIT**. See [`LICENSE`](LICENSE).
- Content (anything in `wiki/`, `raw/`, `outputs/`): **CC BY 4.0**. See [`LICENSE-content`](LICENSE-content).

Contributors are credited in [`CONTRIBUTORS.md`](CONTRIBUTORS.md) on merge. Substantive contributions may also be credited in the paper's acknowledgements section, separately negotiated.

## Questions

For anything not covered above, open a GitHub issue rather than a PR. Discussion-shaped contributions belong in issues; wiki-shaped contributions belong in PRs.
