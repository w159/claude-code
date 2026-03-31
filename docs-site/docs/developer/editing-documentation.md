# Editing this documentation

## Local setup

```bash
cd docs-site
python3 -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
mkdocs serve
```

Open `http://127.0.0.1:8000` and edit files under `docs-site/docs/`. The site reloads on save.

## Conventions

- Use **admonitions** for legal and safety notes (`!!! warning` for proprietary / leak context).
- Prefer **relative links** between pages (`../reference/cli-entry.md` in source becomes sibling URLs when built).
- Add **mermaid** only where diagrams clarify flow; keep [mermaid syntax](https://mermaid.js.org/) compatible with [Material diagrams](https://squidfunk.github.io/mkdocs-material/reference/diagrams/).

## After structural changes

If you add a **new top-level topic** that appears in [Anthropic’s docs index](https://code.claude.com/docs/llms.txt), add a row to [Official docs map](../official-docs-map.md).

## Publishing

Pushing to `main` runs the GitHub Action that deploys to `gh-pages`. Ensure `site_url` in `mkdocs.yml` matches your GitHub Pages base URL.

See also: [Documentation and CI for your own projects](../guides/documentation-and-ci-for-docs.md).
