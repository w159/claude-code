# Developer hub (this repository)

!!! warning "Not an open-source product repo"
This tree is **reconstructed proprietary source**. You can maintain **documentation**, trace **read-only** flow in `src/`, and run small **helper scripts**. You **cannot** legally ship Claude Code from this mirror, and there is no supported way to compile the full CLI here.

## What you can do

| Activity                     | How                                                                                                                    |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| **Preview or extend docs**   | [Editing documentation](editing-documentation.md)                                                                      |
| **Understand control flow**  | [Navigating the source](navigating-the-source.md)                                                                      |
| **Learn build-time gates**   | [Bun bundle and feature flags](bun-bundle-and-feature-flags.md)                                                        |
| **Regenerate appendix data** | `scripts/gen-appendices.sh` at repo root (see [Appendix: environment variables](../appendix/environment-variables.md)) |

## What you cannot do (from this mirror alone)

- Run `npm install` / `bun build` for the full product (no root `package.json`, private graph, `bun:bundle` feature flags).
- Execute a project-wide automated test suite for the CLI (no harness shipped in the reconstruction).

Details: [Reproducibility and limits](../reproducibility.md).

## Related

- [System design: layers](../system-design/layers.md)
- [Official docs map](../official-docs-map.md)
