# Quartz configuration

This folder holds the project's customizations of [Quartz v4](https://github.com/jackyzha0/quartz), the static-site generator that renders `wiki/` to the public site at `https://supgrade.github.io/where-ai-value-lands/`.

Quartz itself is **not** tracked in this repository. It is cloned fresh on every CI build (see `.github/workflows/deploy.yml`) and on every local preview (see "Local preview" below). This keeps the repo clean and makes Quartz upgrades trivial — bump the `--branch` flag in one place.

## What's in this folder

- `quartz.config.ts` — the canonical Quartz configuration for this project. Copied into the Quartz install during build.
- `quartz.layout.ts` — layout overrides (graph exclusions, footer link, breadcrumbs hidden on home).
- `components/scripts/graph.inline.ts` — patched graph script; honours `excludeSlugs` in `Component.Graph()` config.

## How the build works

```
+-------------------+        +------------------+        +---------------+
| this repo         |  --->  | clone quartz/    |  --->  | render wiki/  |
| (wiki/, config)   |        | apply config     |        | output public/|
+-------------------+        +------------------+        +---------------+
                                                                 |
                                                                 v
                                                       +------------------+
                                                       | GitHub Pages     |
                                                       +------------------+
```

The GitHub Action in `.github/workflows/deploy.yml` runs on every push to `main`:

1. Checks out this repo.
2. Clones Quartz v4 into `./quartz/`.
3. Copies `quartz-config/quartz.config.ts` (and optional `quartz.layout.ts`, graph script patch) into the Quartz install.
4. Installs Quartz's dependencies (`npm ci`).
5. Builds the site: `npx quartz build -d ../wiki -o public` (content directory = `wiki/`, output = `quartz/public/`).
6. Uploads `quartz/public` as a GitHub Pages artifact and deploys it.

## Local preview

```bash
# One-time install (from the repo root):
git clone --depth 1 --branch v4 https://github.com/jackyzha0/quartz.git quartz
cp quartz-config/quartz.config.ts quartz/quartz.config.ts
cp quartz-config/quartz.layout.ts quartz/quartz.layout.ts
cp quartz-config/components/scripts/graph.inline.ts quartz/quartz/components/scripts/graph.inline.ts
cd quartz && npm install

# Run the local preview server:
npx quartz build --serve -d ../wiki
```

Quartz hot-reloads at `http://localhost:8080/`.

When you change `quartz-config/quartz.config.ts`, copy it back into `quartz/quartz.config.ts` (the dev server picks up the change on its next build). Or just restart the server.

To pick up a new Quartz upstream version locally, delete the `quartz/` folder and re-clone:

```bash
rm -rf quartz
git clone --depth 1 --branch v4 https://github.com/jackyzha0/quartz.git quartz
cp quartz-config/quartz.config.ts quartz/quartz.config.ts
cp quartz-config/quartz.layout.ts quartz/quartz.layout.ts
cp quartz-config/components/scripts/graph.inline.ts quartz/quartz/components/scripts/graph.inline.ts
cd quartz && npm install
```

## What gets published

All wiki pages are published by default. The build uses `RemoveDrafts` only — pages with `draft: true` in frontmatter are withheld. Do **not** enable `ExplicitPublish` unless every page sets `publish: true`; otherwise the deploy has no `index.html` and GitHub Pages serves the empty RSS feed (`index.xml`) at the site root.

## What gets excluded from the build

The Quartz config's `ignorePatterns` excludes `private`, `templates`, `.obsidian`, and `_staging`. On top of that, Quartz only reads from the content directory we pass via `-d ../wiki`, so by construction nothing outside `wiki/` reaches the build:

- `raw/` — source material, kept private to the repo
- `outputs/` — the interactive HTML lecture pages live on a different surface
- `.claude/` — agent skills, not content
- `.obsidian/` — Obsidian's local state
- Root-level markdown files (`README.md`, `CONTRIBUTING.md`, `CONTRIBUTORS.md`, `CLAUDE.md`, `progress.md`, etc.) — these belong to the repo, not the wiki

## Required GitHub repo settings

Before the first deploy succeeds, configure the repository on GitHub:

1. **Settings → Pages → Source**: select **GitHub Actions**. (Do **not** select "Deploy from a branch" — the workflow uses the modern Actions-based deploy path.)
2. **Settings → Actions → General → Workflow permissions**: set to **Read and write permissions** (or at minimum allow GITHUB_TOKEN to deploy to Pages).
3. The first run may produce environment-protection warnings; if so, **Settings → Environments → delete `github-pages`** and re-run the workflow. Quartz's docs flag this as a common first-time gotcha.

## Customisation notes

The current config uses Quartz's default plugin set with project-specific colors and typography (Source Serif 4 / Source Sans 3 / JetBrains Mono — matching the visual register the `/visualize` skill uses for its HTML lecture pages, see [`wiki/log.md`](../wiki/log.md) entries for examples).

If you want to add custom components or transformers later, drop them in `quartz-config/components/` and a `quartz-config/quartz.layout.ts`, then update the workflow's "Apply project Quartz config" step to copy them in.

## Reference

- Quartz v4 docs: https://quartz.jzhao.xyz/
- Hosting on GitHub Pages: https://quartz.jzhao.xyz/hosting
- Spec for this setup: [`wiki/01_paper-planning/06_collaboration.md`](../wiki/01_paper-planning/06_collaboration.md) §T0, Surface B.
