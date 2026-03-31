# Navigating the `src/` tree

!!! warning "Read-only study"
Use this guide to **read** the reconstruction. Do not treat the tree as a template for redistributing Anthropic’s product.

## Suggested reading order

1. **`main argv` and lifecycle** — `src/main.tsx` (Commander, `preAction`, mode routing).
2. **Interactive path** — `src/replLauncher.tsx`, `src/screens/REPL.tsx` (queue, `onQuery`, UI).
3. **Headless path** — `src/cli/print.ts`, `src/cli/structuredIO.ts`, `src/QueryEngine.ts`.
4. **Core loop** — `src/query.ts` (`queryLoop`), then `src/services/api/client.ts` / `claude.ts`.
5. **Tools** — `src/tools.ts`, `src/Tool.ts`, then a single tool package e.g. `src/tools/BashTool/` and `src/services/tools/`.
6. **MCP** — `src/services/mcp/` and `src/tools/MCPTool/`.

## Maps and indexes

- Top-level layout: [Appendix: directory structure](../appendix/directory-structure.md) (and repo `docs/directory-structure.md`).
- Tool packages: [Appendix: tool packages](../appendix/tool-packages.md).
- Official doc crosswalk: [Official docs map](../official-docs-map.md).

## Search tips

From the repository root:

```bash
# Example: find where a symbol is used
rg "queryLoop" src/query.ts src/ -n

# Example: MCP channel permissions
rg "channelAllowlist" src/services/mcp -n
```

IDE “go to definition” may be incomplete: there is **no** root `tsconfig.json` or `package.json` mirroring Anthropic’s build, so path aliases like `src/...` might not resolve everywhere.

## Deeper subsystems

Use the [Reference](../reference/cli-entry.md) section for per-topic entry points (permissions, compaction, telemetry, bridge, etc.).
