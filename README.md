# doe-bridge.github.io

Source for the [BER Data](https://github.com/doe-bridge) organization landing
page, built with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/)
and published to GitHub Pages via GitHub Actions.

## Stack

- [uv](https://docs.astral.sh/uv/) — Python env + dependency management
- [just](https://github.com/casey/just) — task runner
- [MkDocs Material](https://squidfunk.github.io/mkdocs-material/) — site generator
- GitHub Actions — builds on every push to `main` and deploys to the `gh-pages` branch

## Requirements

- Python 3.11+
- [`uv`](https://docs.astral.sh/uv/getting-started/installation/)
- [`just`](https://github.com/casey/just#installation)

## Local development

```bash
# install deps into a local virtualenv
just install

# serve with live reload at http://localhost:8000
just serve

# build into ./site (with strict mode)
just build
```

Run `just` with no arguments to see all available recipes.

## Editing content

All content lives under [`docs/`](docs/):

- `docs/index.md` — home/landing page
- `docs/projects.md` — project cards
- `docs/team.md` — team members
- `docs/blog/` — blog posts (new posts go in `docs/blog/posts/`)

Site configuration lives in [`mkdocs.yml`](mkdocs.yml).

## Deployment

Pushing to `main` triggers
[`.github/workflows/deploy.yml`](.github/workflows/deploy.yml), which builds
the site with `mkdocs gh-deploy` and force-pushes to the `gh-pages` branch.

One-time setup on GitHub:

1. Repo **Settings → Pages**
2. Set **Source** to **Deploy from a branch**
3. Choose branch **`gh-pages`**, folder **`/ (root)`**

Pull requests run [`.github/workflows/ci.yml`](.github/workflows/ci.yml), which
builds the site in `--strict` mode to catch broken links and warnings.

### Manual deploy

```bash
just deploy
```
