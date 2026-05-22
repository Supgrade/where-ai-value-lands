---
name: lint
description: This skill should be used when the user asks to "lint the wiki", "health check", "check the wiki", "find inconsistencies", "what's broken in the wiki", "audit the wiki", "what's missing", or otherwise wants a periodic structural and substantive review of the wiki. Scans every page in `wiki/`, flags contradictions, orphans, broken wikilinks, missing reverse links, concepts mentioned but lacking their own page, stale hypothesis confidence claims, and produces a tiered report with concrete next actions.
---

# Lint

Periodic health check of the wiki. Wikis decay silently: links drift, claims age out, concepts get mentioned but never get their own page. This skill surfaces that drift so the user can decide what to fix.

`lint` is read-mostly. It reports. It does not silently rewrite pages. Fixes are proposed; the user (or a follow-up `/edit` call) applies them.

## Workflow

### 1. Enumerate the wiki

List every markdown file under `wiki/`. Note: `wiki/index.md` and `wiki/log.md` are special and not linted as content pages.

### 2. Run the checks

Run each of the following passes. Collect findings into the tiered report at the end.

#### Pass A — Link integrity

- **Broken wikilinks.** Every `[[slug]]` must point to a page that exists. Report broken links and the page they appear on.
- **Slug convention.** Slugs are lowercase, hyphen-separated, no spaces. Report violations.
- **Missing reverse links.** For every forward link A → B, page B must reference page A back. Report asymmetries.

#### Pass B — Orphans and hubs

- **Orphans.** Pages with zero inbound wikilinks. May be legitimate (top-level entries, brief, audience) or may be stranded. Report them so the user can judge.
- **Hubs.** Pages with very many inbound links — flag for informational purposes; hubs may be candidates to split if they have grown past ~400 words.

#### Pass C — Missing concept pages

Scan all page bodies for capitalized multi-word phrases or repeated terminology that appears in 2+ pages but does not itself have a page. Examples to look for: "commodification", "rentier capture", "value capture", "L4", "platform layer". Propose creating a page when the term carries real conceptual weight.

#### Pass D — Hypothesis health

For every page in `wiki/02_hypothesis/`:
- Confirm presence of `Status`, `Confidence`, `What would retire this` blocks.
- Compare `Confidence` against the body of evidence in linked source pages. If many sources contradict the hypothesis but `Confidence` is still "high", flag it. If many sources support it but `Confidence` is still "low", flag it.
- Report contradictions explicitly logged inside hypothesis pages — these are not bugs, they are healthy signals; surface them so the user can decide whether the hypothesis still earns its keep.

#### Pass E — Index and log consistency

- Every page on disk should appear in `wiki/index.md`. Report pages missing from the index.
- Every entry in `wiki/index.md` should point to a file that exists. Report stale entries.
- `wiki/log.md` is append-only. Confirm chronological order; flag entries that look rewritten or out of order.

#### Pass F — Stale `last-updated`

Pages whose `last-updated` frontmatter is older than the most recent ingest that touched a related topic. This is a soft signal — flag for review, not for forced rewrite.

### 3. Produce the report

Output a tiered report. Three tiers:

**Tier 1 — Structural (fix soon).** Broken wikilinks. Missing reverse links. Pages missing from the index. Stale index entries pointing to deleted files.

**Tier 2 — Substantive (consider fixing).** Hypothesis confidence misaligned with evidence. Concepts mentioned in multiple pages but lacking a page. Pages over 400 words ripe for splitting.

**Tier 3 — Informational.** Orphans. Hubs. Stale `last-updated` timestamps.

For each finding, give:
- The specific page(s) involved as `[[wikilinks]]`.
- A one-line description of the problem.
- A concrete suggested action (e.g. "add reverse link from [[h1-l0-l7-ladder]] to [[bourdieu-1986]]", "create [[commodification]] page, referenced in 3 pages").

### 4. Suggest next actions

End with a short list:
- "Run `/edit` to apply Tier 1 fixes" (the user can confirm each).
- "Run `/discover` to find sources for [[gap-topic]]" if the lint surfaced unfilled gaps.
- "Run `/ingest` on the queued source in `raw/`" if there is an obvious unaddressed file.

### 5. Append to the log

Append a single entry to `wiki/log.md`:

```markdown
## [YYYY-MM-DD] lint | scope
- T1 findings: N (one-line summary)
- T2 findings: N
- T3 findings: N
```

## What not to do

- Do not auto-fix. `lint` reports, the user (or `/edit`) fixes. Silent rewrites destroy trust.
- Do not flag every stylistic choice. Lint is for structural and substantive drift, not for prose preferences.
- Do not flag a contradiction inside a hypothesis page as a bug. The wiki is supposed to record contradictions; that is a feature.
- Do not skip the reverse-link audit. It is the most common drift mode.
