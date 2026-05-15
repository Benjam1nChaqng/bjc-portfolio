# bjc-portfolio — INDEX

> **Read this first.** Every Claude Code session, every new chat, every mobile planning session.

## What this repo is

`bjc-portfolio` is the meta-repo for Benjamin Chang's AI engineering portfolio. It contains no application code. It contains the **brain** — strategy, decisions, memory, the current meta.

Every project repo (resume-builder, bjc-eval, etc.) cross-references this repo in its own `CLAUDE.md`. New Claude Code sessions load context from `memory/` here before touching code.

## Memory files (read in this order on new sessions)

1. [`memory/01-strategy.md`](memory/01-strategy.md) — The big picture. Win condition. Project pipeline. Why we're doing this.
2. [`memory/02-projects-status.md`](memory/02-projects-status.md) — State of every project. What's shipped, what's WIP, what's planned.
3. [`memory/03-decisions.md`](memory/03-decisions.md) — Architecture decision records (ADRs). Why we chose X over Y.
4. [`memory/04-meta.md`](memory/04-meta.md) — Current AI dev meta. What wows hiring teams in 2026. Updated continuously.
5. [`memory/05-applications.md`](memory/05-applications.md) — Job application tracking. LinkedIn / Mercor / Handshake / Surge status.
6. [`memory/06-open-questions.md`](memory/06-open-questions.md) — Research queue. Open decisions awaiting input.

## Portfolio architecture

```
bjc-platform/
├── bjc-portfolio/        ← THIS REPO (memory + strategy)
├── resume-builder/       ← Project 1 (Next.js + agents)
├── bjc-eval/             ← Project 2 (Python + Inspect AI eval harness)
├── bjc-mcp-*/            ← Project 3+ (custom MCP servers)
├── bjc-agents/           ← (future) shared agent primitives
└── bjc-traces/           ← (future) observability layer
```

## How to add a new memory file

1. Create `memory/NN-topic.md` (next sequential number)
2. Add link to this INDEX
3. Commit with message `memory: add NN-topic`

## Rules

- **Memory files are append-mostly.** When something changes, note the change at the bottom with a date. Old facts stay as history.
- **Decision records are immutable.** Add a new ADR superseding the old one; never edit history.
- **Honest > impressive.** If a benchmark came in at κ=0.42, the file says κ=0.42.
- **Phone Claude (web/mobile) can write to these via artifact downloads.** Owner commits them.
- **Claude Code reads these on session start before touching any code.**

---

**Owner**: Benjamin Chang
**GitHub**: github.com/Benjam1nChaqng (rename pending)
**Last reviewed**: 2026-05-14
