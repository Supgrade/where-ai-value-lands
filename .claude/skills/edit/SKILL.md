---
name: edit
description: This skill should be used when the user asks to "edit the wiki", "update the page on X", "rename this page", "split this page", "merge these pages", "remove this source", "delete the page on Y", "fix this in the wiki", or otherwise wants a structured change to wiki content. Applies the change while maintaining link integrity (forward + reverse), updating `wiki/index.md`, and appending to `wiki/log.md`.
---

# Edit

Applies user-requested changes to the wiki while preserving its structural invariants. Most edits during the inquiry will come through `/ingest` and `/ask` automatically. `edit` is for everything else: renames, splits, merges, deletions, and direct content fixes.

The invariants this skill must preserve:

- Slug convention (lowercase, hyphen-separated, no spaces).
- Wikilink syntax `[[slug]]`.
- Forward → reverse link symmetry (if A links B, B references A).
- `wiki/index.md` lists every page on disk and nothing else.
- `wiki/log.md` is append-only.

## Workflow

### 1. Confirm the change

Restate the requested change in one line. If it touches more than one page (rename, split, merge, delete), enumerate the affected pages and ask the user to confirm scope before acting. Structural changes are easy to break and hard to reverse.

### 2. Apply

Use the appropriate sub-flow:

**Update content of a single page.** Edit the page. Update `last-updated`. If the edit introduces new wikilinks, add the reverse link on the target page.

**Rename a page (change the slug).** Update the file path. Find every page that links to the old slug and rewrite to the new slug. Update `wiki/index.md`. The forward → reverse rule means the reverse links also need to point at the new slug.

**Split a page.** Create the new page(s) with clear slugs. Move the relevant section(s) out of the original page. Add wikilinks both directions between original and new pages. Update `wiki/index.md` with new entries.

**Merge pages.** Pick the canonical destination. Move content from the merged page into the destination, preserving wikilinks. Find every page that linked to the merged page and rewrite to the destination. Delete the merged page. Remove its entry from `wiki/index.md`.

**Delete a page.** Confirm with the user that the page is genuinely unwanted (not just stale). Find every page that links to it and either remove the link or replace with a successor. Delete the file. Remove its entry from `wiki/index.md`. Note in `log.md` that the page was removed.

**Remove a source.** Delete the source summary page. Remove citations from concept and hypothesis pages that drew from it, or mark them as `[citation lost — source removed YYYY-MM-DD]` if the claim still stands without the source. Update `wiki/index.md`. The source file in `raw/` is the user's; do not delete it unless asked.

### 3. Audit link integrity

After the change, do a quick pass:

- Every wikilink in changed pages still resolves.
- Every reverse link still resolves.
- `wiki/index.md` reflects current disk state.

If any of these fail, fix them before reporting done.

### 4. Append to the log

```markdown
## [YYYY-MM-DD] edit | brief description
- Action: rename | split | merge | delete | update
- Pages affected: [[a]], [[b]], [[c]]
```

### 5. Report

Brief summary: what changed, what links were updated, anything the user should double-check.

## What not to do

- Do not rename, split, merge, or delete without restating the change and getting confirmation when scope crosses more than one page.
- Do not delete files in `raw/` unless explicitly told. `raw/` is the user's dump zone.
- Do not rewrite `wiki/log.md`. Append only.
- Do not let `wiki/index.md` drift from disk state.
- Do not leave orphan reverse links after a rename or delete.
