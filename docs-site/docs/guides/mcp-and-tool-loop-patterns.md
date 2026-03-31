# MCP and tool-loop patterns (abstract)

!!! note "Conceptual only"
This page describes **common agent architectures**. It references `src/` modules only as **illustrations** of where similar ideas appear in Claude Code—not as code to copy.

## Tool loop (functions / tools)

1. Define tools with **names, descriptions, and JSON Schema** (or equivalent) for arguments.
2. Send user + conversation + tool definitions to the model.
3. If the model returns a **tool call**, validate arguments, **execute** on the host, append a **tool_result** message (or provider-specific equivalent).
4. Repeat until the model finishes without further tool calls or a cap is hit.

In this reconstruction, much of that orchestration lives in `query.ts` and adjacent helpers, while tool implementations live under `tools/*` and `services/tools/`.

## MCP (Model Context Protocol)

**MCP** standardizes how tools and resources are exposed by **servers** the host spawns and talks to over stdio or other transports. Claude Code’s `services/mcp/` implements configuration, transports, OAuth, and channel-style push—see **[MCP reference](../reference/mcp.md)** for file-level mapping.

For **your** project:

- Start from [MCP documentation](https://modelcontextprotocol.io) and official SDKs.
- Implement **one** small MCP server (e.g. filesystem or git) before designing a full IDE-quality integration.

## Parallel: skills and plugins

Claude Code layers **skills** (project-scoped instructions + commands) and **plugins** on top of the core loop. Greenfield designs might use: simple slash-commands, `SKILL.md` conventions, or dynamic imports—without reproducing this product’s plugin manifest.

## See also

- [Building an agentic CLI overview](building-an-agentic-cli-overview.md)
- [Official: MCP](https://code.claude.com/docs/en/mcp)
