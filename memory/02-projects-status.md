# 02 — Projects Status

> Current state of every project. Append updates with date stamps. Never delete history.

## bjc-portfolio (this repo)

- **Status**: Bootstrapped 2026-05-14
- **Contents**: INDEX.md, 6 memory files
- **Next**: keep memory files current as projects evolve
- **Demo URL**: github.com/Benjam1nChaqng/bjc-portfolio (rename pending)

---

## resume-builder

- **Status**: v0.2 in autonomous build (as of 2026-05-14 evening)
- **Stack**: Next.js 15, TypeScript, Vercel, Vercel Blob, Claude Sonnet 4.6, Zod
- **Current chunk**: 7–8 (autonomous Claude Code run at home; PowerShell session not to be touched)
- **What's working**: 
  - Resume import (Chunks 1–4)
  - JD parsing scaffold
  - Internal bullet-tailoring agent
- **What's broken / blocked**:
  - **Vercel `BLOB_READ_WRITE_TOKEN` deploy issue** — env var not propagating. Likely a store-namespaced name like `RESUME_PDFS_READ_WRITE_TOKEN`, or propagation delay. Resolve before recording Loom.
- **Stop condition**: v0.2 (JD scrape + bullet tailor + diff view functional + deployed). **Do not grind to v1.0.**
- **Time remaining**: ~5–8 hours (UI wiring after Chunks 7–8 + Loom + README)
- **Demo asset (TODO)**: 90-second Loom: import → tailor → diff

---

## bjc-eval (formerly swe-judge)

- **Status**: v0.1 scaffolded — 48 passing tests, CLI verified end-to-end via in-process smoke test
- **Code location**: built on Claude container in `/home/claude/swe-judge/` (will be tarball-packaged for owner download)
- **Stack**: Python 3.11+, Pydantic v2, Typer, Rich, Anthropic SDK, OpenAI SDK, Google Generative AI SDK, scikit-learn, simpledorff, ulid-py
- **Optional**: `[inspect]` extra for Inspect AI integration
- **Build coverage**:
  - ✅ Pydantic data models (Task, Run, Score, JudgmentResult, HumanScore)
  - ✅ 3-dimension rubric (CORRECTNESS, CODE_QUALITY, REASONING) with worked anchors 1–5
  - ✅ Shared judge system prompt (fairness property)
  - ✅ Judge protocol + 4 implementations (MockJudge, Anthropic, OpenAI, Google)
  - ✅ Inter-rater reliability: Cohen's κ pairwise + judge-vs-human + Krippendorff's α
  - ✅ SQLite storage layer with FK constraints
  - ✅ Parallel runner via ThreadPoolExecutor (task × judge fan-out)
  - ✅ Typer CLI: `swe-judge run` + `swe-judge report`
  - ✅ 5-task seed dataset (bug_fix × 2, test_write × 2, code_review × 1)
  - ✅ README with citations (CALM, JudgeBench, Inspect AI, Landis & Koch)
- **Pending before public release**:
  - CLAUDE.md cross-reference to bjc-portfolio memory
  - .gitignore
  - LICENSE (MIT)
  - .github/workflows/ci.yml
  - CHANGELOG.md
  - Expand dataset from 5 → 50 examples
  - Recruit 1–2 humans for ground-truth scoring on 20 items
  - Run real 3-judge ensemble and publish κ numbers honestly
- **Stop condition**: v0.1 with measured κ numbers + clean README + live repo
- **Time remaining**: ~25–35 hours
- **Differentiator**: Dataset is contamination-free (vs. known contamination in SWE-bench Verified). Mention prominently in README.

---

## bjc-mcp-* (Project 3)

- **Status**: Not started
- **Decision pending**: Which domain? Candidates:
  - `bjc-mcp-github-personal` — owner's commits, PRs, issues across repos
  - `bjc-mcp-calendar` — calendar + task integration
  - `bjc-mcp-strava` — fitness data (if owner uses Strava)
  - `bjc-mcp-files` — local file search MCP
- **Criteria**: must use data the owner already has access to, must solve a real annoyance, must be small enough to ship in ~20 hours
- **Stack target**: TypeScript MCP SDK
- **Demo strategy**: video showing Claude Desktop using the server to do something useful on the owner's actual data

---

## Future projects (gated on first contract not landing)

- **bjc-agents** — shared agent primitives library extracted from resume-builder
- **bjc-traces** — OpenTelemetry observability layer for agent runs
- **bjc-eval extensions** — adversarial red-team agents, verdict-balanced few-shot calibration experiments

---

## Cross-project asks

- **GitHub username rename**: `Benjam1nChaqng` → cleaner (suggested: `benjaminchang` or `bjchang`). Do before first application.
- **LinkedIn government-ID verification**: CLEAR or Persona. Required for AI Labor Marketplace credibility.
- **Domain purchase**: optional. `bjchang.dev` or similar for a static portfolio page linking the repos.

---

## Updates log

- **2026-05-14**: File created. resume-builder mid-Chunks 7–8 autonomous build. bjc-eval scaffolded with 48 tests. bjc-mcp domain TBD.
