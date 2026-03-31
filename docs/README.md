# Documentation

The **MkDocs site** (for GitHub Pages) lives in **`docs-site/`**.

- Source pages: `docs-site/docs/`
- Local preview: `cd docs-site && python3 -m venv .venv && source .venv/bin/activate && pip install -r requirements.txt && mkdocs serve`

The file **`directory-structure.md`** in this folder remains a quick `src/` layout reference duplicated in the site under **Appendix → Directory structure**.

The published site also includes **System design**, **Developer**, **Guides** (greenfield agent CLI + docs CI), and **Glossary**; see navigation in `docs-site/mkdocs.yml`.
