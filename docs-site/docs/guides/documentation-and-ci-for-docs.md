# Documentation and CI (pattern from this repo)

You can reuse the **same mechanics** this project uses for **any** open-source or internal project docs—not Claude Code itself.

## Ingredients

| Piece           | Location here                                                                                                         |
| --------------- | --------------------------------------------------------------------------------------------------------------------- |
| **Static site** | [MkDocs](https://www.mkdocs.org/) + [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)               |
| **Sources**     | `docs-site/docs/**/*.md`, `docs-site/mkdocs.yml`                                                                      |
| **Build**       | `mkdocs build -f docs-site/mkdocs.yml`                                                                                |
| **Deploy**      | GitHub Actions → `gh-pages` branch (e.g. [peaceiris/actions-gh-pages](https://github.com/peaceiris/actions-gh-pages)) |

## Checklist for a new repo

1. Add `docs-site/` with `mkdocs.yml`, `requirements.txt`, and Markdown under `docs/`.
2. Set `site_url` when GitHub Pages URL is known.
3. Add workflow: Python setup → `pip install -r docs-site/requirements.txt` → `mkdocs build` → deploy `docs-site/site`.
4. Enable **GitHub Pages** from `gh-pages` / root (or switch to GitHub’s native Pages Actions upload).
5. Use `enable_jekyll: false` (or commit `.nojekyll`) so Jekyll does not skip underscore paths.

## This fork’s live site

Configured `site_url`: [https://mehmoodosman.github.io/claude-code-source-code/](https://mehmoodosman.github.io/claude-code-source-code/)

## See also

- [Installation](../installation.md) — local preview commands
- [Editing documentation](../developer/editing-documentation.md)
