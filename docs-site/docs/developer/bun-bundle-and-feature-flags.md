# Bun bundle and feature flags

The shipping Claude Code CLI is built with **Bun** and internal **`bun:bundle`** integration. In the recovered source, `src/main.tsx` uses compile-time feature gates such as:

- `feature('KAIROS')` — lazy `require` of `assistant/` (assistant / Agent SDK–oriented paths).
- `feature('COORDINATOR_MODE')` — lazy `require` of `coordinator/coordinatorMode`.
- `feature('VOICE_MODE')` — conditional `useVoiceIntegration` in `REPL.tsx`.

## What `feature()` means here

In Anthropic’s pipeline, `feature('…')` is almost certainly a **constant** resolved at bundle time: dead branches are stripped from the published `cli.js`. The reconstruction **contains all branches** as TypeScript, so you can read “internal” code paths that might not ship in every npm artifact.

## Implications for “building from source”

A normal `tsc` or `bun build` **without** Anthropic’s bundler will not reproduce:

- The same dead-code elimination.
- The same `bun:bundle` API semantics.
- The same proprietary dependency closure.

That is one reason [Reproducibility and limits](../reproducibility.md) states you cannot rebuild the shipping binary from this mirror.

## See also

- [System design: layers](../system-design/layers.md)
- [CLI entry reference](../reference/cli-entry.md)
