# Building your own agentic coding CLI (greenfield)

!!! danger "Do not clone proprietary code"
This page describes how to build **new** tooling from **public** APIs and OSS patterns. It is **not** instructions to copy or redistribute the leaked `src/` tree as “open-source Claude Code.” Anthropic’s Claude Code remains **proprietary**.

## What “agentic CLI” means

A minimal agent loop:

1. **Context** — project files, git status, user prompt.
2. **Model** — calls a capable LLM API with tools/functions defined in schema form.
3. **Tools** — read/write files, grep, run shell (with guardrails), call HTTP, etc.
4. **Loop** — model requests tools → host executes → results appended → model continues until done.

Claude Code implements this pattern in TypeScript with extra product layers (trust, compaction, MCP, IDE bridge). Your project can be far smaller.

## Stack options (all legitimate OSS / vendor SDKs)

| Piece             | Common choices                                                                                                       |
| ----------------- | -------------------------------------------------------------------------------------------------------------------- |
| **Runtime**       | Node.js, Bun, Deno, Go, Python                                                                                       |
| **Terminal UI**   | None (pure stdin/stdout), [Ink](https://github.com/vadimdemedes/ink) (React), blessed, bubbletea                     |
| **CLI parsing**   | Commander, yargs, clap (Rust), Typer (Python)                                                                        |
| **Anthropic API** | Official [Anthropic SDK](https://docs.anthropic.com/) and [Messages API](https://docs.anthropic.com/en/api/messages) |
| **MCP**           | [Model Context Protocol](https://modelcontextprotocol.io) SDKs and server examples                                   |
| **Sandboxes**     | Containers, `firejail`, allow-listed commands, separate VMs (depends on threat model)                                |

## OSS / public projects to study (examples, not endorsements)

Look for **actively maintained** agent or coding assistants under licenses you accept. Examples people often cite in the ecosystem include **Aider**, terminal agents built on **Continue** or **Codex-style** CLIs, and **MCP servers** in the official registry. **Compare licenses and security posture yourself**—do not assume parity with Claude Code.

## Relationship to this repository

Use the `src/` mirror to **learn patterns** (how compaction, MCP, or permissions _can_ be structured). Re-implement ideas in **your own codebase** with your own naming and design; do not paste Anthropic’s source into a public repo.

## Next

- [MCP and tool-loop patterns](mcp-and-tool-loop-patterns.md) — abstract loop without copying this tree.
- [Documentation and CI](documentation-and-ci-for-docs.md) — ship docs like this site.
