# Glossary

Short definitions for terms used across this site and the `src/` tree. Authoritative product wording remains in [official Claude Code docs](https://code.claude.com/docs/en/overview).

| Term                 | Meaning (in this codebase)                                                                                                                |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| **Agent / teammate** | Secondary model actors coordinated with the main session; implemented largely in `utils/swarm/`.                                          |
| **Compaction**       | Reducing or rewriting transcript/history to fit context limits; `services/compact/`.                                                      |
| **Coordinator**      | Internal multi-agent coordination feature gated by `COORDINATOR_MODE`; `coordinator/`.                                                    |
| **GrowthBook**       | Feature-flag / experiment client for product behaviors; `services/analytics/growthbook.ts`.                                               |
| **Headless / print** | Non-TUI mode with structured stdin/stdout; `cli/print.ts`, `QueryEngine.ts`.                                                              |
| **KAIROS**           | Bundle-time gate for assistant-oriented code paths; `assistant/`.                                                                         |
| **MCP**              | Model Context Protocol; `services/mcp/`, MCP tools under `tools/`.                                                                        |
| **REPL**             | Interactive terminal UI session; `screens/REPL.tsx`.                                                                                      |
| **Session hooks**    | User-configured shell hooks on lifecycle events; see `utils/sessionStart.ts` and official [Hooks](https://code.claude.com/docs/en/hooks). |
| **Swarm**            | Implementation umbrella for teammate spawning (tmux, iTerm, in-process); `utils/swarm/`.                                                  |
| **Teleport**         | Session handoff / remote resume flows; `utils/teleport/`, related API modules.                                                            |
| **Tool loop**        | Alternation between model streaming and tool execution until the turn completes; centered on `query.ts`.                                  |
| **Trust**            | User acknowledgement of workspace risk before applying project config; wired from `main.tsx` / config utilities.                          |
| **VOICE_MODE**       | Compile-time gate for voice dictation in the REPL; `voice/`.                                                                              |
