# lobs-ai

This is [Rafe Symonds](https://rafesymonds.com)'s AI agent org, which is the home of Lobs, a personal AI runtime built from scratch. Rafe is a CS grad student at the University of Michigan. He also co-founded [PAW Engineering](https://paw-engineering.com), a collaborative hosting platform.

Lobs is a local-first system that orchestrates AI agents — it calls LLMs directly, runs tools locally, manages its own memory, and coordinates multi-step workflows. It grew up inside [OpenClaw](https://openclaw.dev), a powerful AI coding tool that Rafe used daily. OpenClaw is great — the custom build wasn't about escaping its limitations. Rafe is preparing to teach **EECS 498: Applied Agentic Software Engineering** at UMich, and building toward agentic AI as a career path. The only way to teach this deeply is to have built it from scratch yourself. Three months of daily iteration later, Lobs stands on its own.

**Lobs website:** [lobslab.com](https://lobslab.com) · **Personal site:** [rafesymonds.com](https://rafesymonds.com) · **PAW:** [paw-engineering.com](https://paw-engineering.com)

---

## Core System

| Repo | What it does |
|------|-------------|
| [**lobs-core**](https://github.com/lobs-ai/lobs-core) | The engine. TypeScript agent runtime with LLM execution loop, orchestrator, task workflows, context engine, Discord bot, voice pipeline, live meeting transcription, and CLI. |
| [**lobs-nexus**](https://github.com/lobs-ai/lobs-nexus) | Web dashboard (React/Vite). Task management, worker monitoring, agent chat, live meeting transcription, brain dump capture, real-time system view. |
| [**lobs-memory**](https://github.com/lobs-ai/lobs-memory) | Persistent search server. Hybrid BM25 + vector search, neural reranking, file watching, temporal decay. |
| [**lobs-vim**](https://github.com/lobs-ai/lobs-vim) | Neovim plugin. AI coding agent where reasoning runs on the server, tools execute locally in your editor. |
| [**lobs-brain**](https://github.com/lobs-ai/lobs-brain) | Agent personality, memory, learnings, project docs, and agent configs. The knowledge base that persists across sessions. Private. |

## Integrations & Tools

| Repo | What it does |
|------|-------------|
| [**lobs-sentinel**](https://github.com/lobs-ai/lobs-sentinel) | Persistent single-purpose AI agents for GitHub — PR review, issue triage, auto-labeling. Runs in Docker. |
| [**lobs-voice**](https://github.com/lobs-ai/lobs-voice) | Local STT + TTS sidecar services for Discord voice integration. Whisper.cpp for speech-to-text, Chatterbox for text-to-speech. |
| [**lobs-meeting-transcriber**](https://github.com/lobs-ai/lobs-meeting-transcriber) | Transcribes meetings and feeds them into agent memory. |
| [**lobs-youtube-ingester**](https://github.com/lobs-ai/lobs-youtube-ingester) | YouTube content ingestion into searchable agent memory. |
| [**lobs-memory-plugin**](https://github.com/lobs-ai/lobs-memory-plugin) | OpenClaw plugin for lobs-memory search integration. |
| [**lobs-imagine**](https://github.com/lobs-ai/lobs-imagine) | Local image generation service (Stable Diffusion on MPS). Private. |

## Legacy / Earlier Iterations

These repos are from earlier versions of the system. Kept public for reference — lobs-core is the current runtime.

| Repo | What it was |
|------|------------|
| [**lobs-server**](https://github.com/lobs-ai/lobs-server) | v4/v5-era Python server (replaced by lobs-core TypeScript rewrite). |
| [**lobs-orchestrator**](https://github.com/lobs-ai/lobs-orchestrator) | v5-era Python orchestrator (now built into lobs-core). |
| [**lobs-dashboard**](https://github.com/lobs-ai/lobs-dashboard) | Early Swift/macOS dashboard (replaced by lobs-nexus). |
| [**lobs-mission-control**](https://github.com/lobs-ai/lobs-mission-control) | Swift macOS app for system monitoring (replaced by lobs-nexus). |
| [**lobs-mobile**](https://github.com/lobs-ai/lobs-mobile) | iOS companion app. |
| [**lobs-mcp**](https://github.com/lobs-ai/lobs-mcp) | MCP (Model Context Protocol) server for lobs-core. |

## Apps

Side projects built with/alongside the agent system.

| Repo | What it is |
|------|-----------|
| [**lobslab-apps**](https://github.com/lobs-ai/lobslab-apps) | Web apps hosted on lobslab.com — Crapuler (UMich course watchlist), Ballz (physics sandbox), Stellar Siege (cosmic RTS). Docker + Caddy. |

## Other

| Repo | |
|------|---|
| [**lobs-ai.github.io**](https://github.com/lobs-ai/lobs-ai.github.io) | Public website at [lobslab.com](https://lobslab.com). Architecture deep-dive, build timeline, war stories. |
| [**lobslab-infra**](https://github.com/lobs-ai/lobslab-infra) | Infrastructure and deployment for lobslab.com services. Docker Compose, Caddy config, monitoring. |
| [**over-the-horizon**](https://github.com/lobs-ai/over-the-horizon) | iOS AR app — overlays location names on live camera feed. |
| [**grandmas-stories**](https://github.com/lobs-ai/grandmas-stories) | iOS app for recording and sharing family stories. |

---

## Configuration

All identity and environment-specific values are config-driven — no hardcoded emails, Discord IDs, or URLs in the source. Config lives in `~/.lobs/config/`:

```bash
~/.lobs/config/
├── lobs.json      # Git identity, gateway settings
├── discord.json   # Bot token, owner ID, channel policies
├── models.json    # LLM model configuration
└── google.json    # Google OAuth settings
```

See each repo's README for full config schema.

## How It Works

```
You (Neovim / Dashboard / Discord / CLI)
        │
        ▼
   ┌─────────┐
   │lobs-core │ ← Orchestrator, agent runner, context engine
   └────┬─────┘
        │
   ┌────┴────────────────────┐
   │                         │
   ▼                         ▼
┌──────────┐          ┌───────────┐
│lobs-nexus│          │lobs-memory│
│(dashboard)│          │ (search)  │
└──────────┘          └───────────┘
```

lobs-core is the brain. It takes tasks, spins up worker agents (programmer, reviewer, architect, researcher, writer), calls LLMs (Anthropic, OpenRouter, local models via LM Studio), executes tools, and manages the full lifecycle. Memory persists across sessions via lobs-memory. The dashboard and vim plugin are interfaces into the same system.

## Built by

[Rafe Symonds](https://github.com/RafeSymonds) — because the best way to have a good AI agent is to build one yourself. And the best way to teach it is to have done exactly that.
