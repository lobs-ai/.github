# lobs-ai

This is [Rafe Symonds](https://rafesymonds.com)'s AI agent org. He builds AI systems — Lobs (personal agent runtime) and Squad (open-source multi-agent platform). CS grad student at the University of Michigan.

**Squad:** [github.com/lobs-ai/squad](https://github.com/lobs-ai/squad) · **LobsLab:** [lobslab.com](https://lobslab.com) · **PAW:** [paw-engineering.com](https://paw-engineering.com)

---

## Squad · The Flagship Project

**Open-source multi-agent orchestration.** Gateway-centric, connector-based, Docker-first. Subagents, tasks, and ask-user as native protocol primitives — not markdown hacks.

- **Gateway-centric** — All agents register with the gateway. Session management, routing, and auth in one place.
- **Connector ecosystem** — Discord, Slack, HTTP, CLI. One agent, many faces.
- **Native primitives** — Tasks, subagents, and ask-user are first-class protocol types. Parallel execution without race conditions.
- **24 LLM providers** — OpenAI, Anthropic, Google, xAI, Mistral, Groq, and 19 more. Swap providers with a config change.
- **Plugin API** — Hooks for every lifecycle event. Memory, tools, post-processing.
- **Docker-first** — One command to run everything.

```
git clone https://github.com/lobs-ai/squad.git
cd squad
docker compose up
```

---

## Lobs · Personal AI Runtime

Lobs is Rafe's personal AI system — a TypeScript runtime that orchestrates specialized agents, calls LLMs, runs tools locally, manages its own memory, and coordinates multi-step workflows.

| Repo | What it does |
|------|-------------|
| [**lobs-core**](https://github.com/lobs-ai/lobs-core) | Engine. Agent runtime with LLM execution loop, orchestrator, task workflows, context engine, Discord bot, voice pipeline, and CLI. |
| [**lobs-nexus**](https://github.com/lobs-ai/lobs-nexus) | Web dashboard — task management, worker monitoring, agent chat, live meeting view. |
| [**lobs-memory**](https://github.com/lobs-ai/lobs-memory) | Search server. Hybrid BM25 + vector search with neural reranking. |
| [**lobs-vim**](https://github.com/lobs-ai/lobs-vim) | Neovim plugin. AI coding agent with server-side reasoning and local tool execution. |
| [**companion**](https://github.com/lobs-ai/companion) | macOS desktop agent with permanent memory and project context. |
| [**agentic**](https://github.com/lobs-ai/agentic) | Modular TypeScript toolkit extracted from production code. LLM client, tool executor, memory, runner, config. |

### Integrations & Tools

| Repo | What it does |
|------|-------------|
| [**lobs-sentinel**](https://github.com/lobs-ai/lobs-sentinel) | GitHub agents for PR review and issue triage. |
| [**lobs-voice**](https://github.com/lobs-ai/lobs-voice) | STT + TTS sidecars for Discord. Whisper.cpp + Chatterbox. |
| [**lobs-meeting-transcriber**](https://github.com/lobs-ai/lobs-meeting-transcriber) | Meeting transcription into agent memory. |
| [**lobs-youtube-ingester**](https://github.com/lobs-ai/lobs-youtube-ingester) | YouTube ingestion into searchable memory. |
| [**lobs-memory-plugin**](https://github.com/lobs-ai/lobs-memory-plugin) | OpenClaw plugin for lobs-memory search. |
| [**lobs-mobile**](https://github.com/lobs-ai/lobs-mobile) | iOS companion app. Task management, push notifications, agent chat on the go. |
| [**lobs-mcp**](https://github.com/lobs-ai/lobs-mcp) | MCP server — Model Context Protocol integration for Lobs as an AI tool backend. |

### Legacy (replaced by lobs-core)

| Repo | What it was |
|------|------------|
| lobs-server | v4/v5 Python server |
| lobs-orchestrator | v5 Python orchestrator |
| lobs-dashboard | Early Swift dashboard |
| lobs-mission-control | Swift system monitor |

---

## Side Projects & Experiments

| Repo | What it is |
|------|-----------|
| [**cortex**](https://github.com/lobs-ai/cortex) | Structured-first executive assistant. Postgres-backed task/calendar reasoning with four AI roles. |
| [**jot**](https://github.com/lobs-ai/jot) | Local AI note-taking CLI. Natural language capture, local model analysis. |
| [**agent-replay**](https://github.com/lobs-ai/agent-replay) | Replay debugger for agent runs — timeline, flamegraph, step-through UI. |
| [**hive**](https://github.com/lobs-ai/hive) | Multi-agent coordination system. |
| [**study-buddy**](https://github.com/lobs-ai/study-buddy) | AI study companion. |
| [**prototypes**](https://github.com/lobs-ai/prototypes) | Experimental prototypes. |
| [**over-the-horizon**](https://github.com/lobs-ai/over-the-horizon) | iOS AR app — overlays location names on live camera feed. |
| [**grandmas-stories**](https://github.com/lobs-ai/grandmas-stories) | iOS app for recording family stories. |
| [**lobslab-apps**](https://github.com/lobs-ai/lobslab-apps) | Web apps on lobslab.com — Crapuler, Ballz, Stellar Siege. Docker + Caddy. |
| [**lobslab-infra**](https://github.com/lobs-ai/lobslab-infra) | Infrastructure as code for lobslab.com — Docker Compose, Caddy, Cloudflare, and deployment configs. |

---

## Built by

[Rafe Symonds](https://github.com/RafeSymonds)
