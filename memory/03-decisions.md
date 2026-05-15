# 03 — Decisions (ADRs)

> Architecture Decision Records. **Immutable.** When a decision changes, write a NEW ADR that supersedes the old one. Never edit history.

Format: each ADR is numbered, dated, and ends with a status (`Accepted` / `Superseded by ADR-XXX` / `Rejected`).

---

## ADR-001 — Portfolio architecture is platform ecosystem, not monolith

**Date**: 2026-05-14
**Status**: Accepted

**Context**: Owner initially wanted "one all-knowing project" that combines resume-builder + eval + everything.

**Decision**: Reject the monolith. Build `bjc-platform` ecosystem of focused repos that share infrastructure. Mirrors how Anthropic itself ships (`claude-code` + `inspect_ai` + `anthropic-sdk-python` + `claude-cookbooks` — not one mega-repo).

**Consequences**:
- Each repo is independently demoable and stress-testable
- Hiring teams see platform-level thinking, not feature-stuffing
- Higher git/CI/deploy overhead, but reusable across all projects
- Portfolio unity comes from shared `bjc-portfolio/memory/` + cross-references, not packaging

---

## ADR-002 — Memory lives in git-versioned files

**Date**: 2026-05-14
**Status**: Accepted

**Context**: Chat context compaction loses information. Owner concerned about losing vital decisions and progress between sessions.

**Decision**: All durable knowledge (strategy, decisions, project status, current meta, applications, open questions) lives in markdown files in `bjc-portfolio/memory/`. Every Claude Code session reads `INDEX.md` first. Mobile Claude (web/app) creates files via artifact downloads; owner commits them.

**Consequences**:
- Zero context loss from compaction
- Git history is the audit log
- Modest overhead per session (loading memory files)
- Cross-session continuity becomes a feature, not a hope

---

## ADR-003 — bjc-eval stack: Python 3.11 + Inspect AI + Pydantic v2

**Date**: 2026-05-14
**Status**: Accepted

**Context**: Choose stack for the LLM evaluation harness.

**Decision**: Python 3.11+. Pydantic v2 for data models. Typer + Rich for CLI. scikit-learn + simpledorff for reliability stats. Inspect AI as optional extra for integration.

**Rationale**:
- Inspect AI is Anthropic's open-source eval framework, used by DeepMind, Grok, UK AISI. Tier S signal.
- Python is the lingua franca of ML/eval work.
- Pydantic v2 is the modern type-safe data validation layer; matches what production AI labs use.
- Typer + Rich produces CLIs that look professional in screenshots/Looms.

**Rejected alternatives**:
- TypeScript + Mastra — TS eval tooling is less mature; hiring signal weaker.
- LangChain — too heavy, often the wrong abstraction.
- Roll-your-own everything — fails the "fluent in modern tools" signal.

---

## ADR-004 — 3-judge ensemble: Claude Opus 4.7 + GPT-5.2 + Gemini 3 Pro

**Date**: 2026-05-14
**Status**: Accepted

**Context**: Single-judge LLM-as-judge work is 2024-coded and known-biased.

**Decision**: Ensemble of 3 judges, one from each major frontier lab. All share the same system prompt and tool schema. Inter-judge κ is a primary reported metric.

**Rationale**:
- Diversity across model families reduces correlated bias
- CALM framework (Ye et al., ICLR 2025) identifies 12 LLM judge biases; ensemble + bias mitigations address most
- Reporting inter-judge κ honestly signals epistemic discipline

**Bias mitigations applied**:
- Shared system prompt (fairness)
- Forced tool use with identical schema (output format normalization)
- Evidence-first reasoning required
- Position randomization where applicable

---

## ADR-005 — bjc-eval v0.1 scope freeze: 50 examples, 3 categories, 3 judges, 3 dimensions

**Date**: 2026-05-14
**Status**: Accepted

**Context**: Scope creep is the #1 portfolio killer.

**Decision**: v0.1 = 50 dataset items across 3 categories (bug_fix, test_write, code_review) × 3 judges × 3 rubric dimensions (CORRECTNESS, CODE_QUALITY, REASONING) + 20 human-scored ground-truth items. **Stop. Ship. Move on.**

**Consequences**:
- Forces "good enough is good enough" discipline
- Leaves room for v0.2 only if a hiring conversation specifically requests it
- Prevents endless tweaking that delays applications

---

## ADR-006 — resume-builder stops at v0.2

**Date**: 2026-05-14
**Status**: Accepted

**Context**: Resume-builder is Project 1 of 3. Spending unlimited time on it starves the rest of the portfolio.

**Decision**: Hard cap at v0.2 (JD scrape + bullet tailor + diff view + deployed + Loom). Any further polish goes into README and demo video, not features.

**Consequences**:
- Frees ~30+ hours for bjc-eval
- Loom + README do the heavy lifting for hiring teams
- Owner must resist the urge to add "just one more feature"

---

## ADR-007 — Honesty rule: report actual κ numbers even if bad

**Date**: 2026-05-14
**Status**: Accepted

**Context**: Tempting to cherry-pick favorable benchmark runs.

**Decision**: Every published metric is the real one. If inter-judge κ comes in at 0.42, the README says 0.42. If a judge disagrees with humans 40% of the time, that goes in the README.

**Rationale**:
- Hiring teams pay $150/hr for engineers with epistemic integrity
- A measured κ of 0.42 with an honest analysis of *why* is more impressive than a fabricated 0.85
- Discoverable dishonesty (someone re-runs the eval) is career-ending

---

## ADR-008 — Outlier permanently blocked

**Date**: 2026-05-14
**Status**: Accepted

**Context**: Outlier (Scale AI) is a candidate platform for AI Trainer roles.

**Decision**: Do not apply to Outlier. California Working Location Policy excludes CA-based contractors due to AB5 / Prop 22 legal exposure.

**Consequences**:
- Removes one option from the funnel
- Concentrates effort on LinkedIn AI Labor Marketplace, Mercor, Handshake AI, Surge AI

---

## ADR-009 — Local PowerShell + Claude Code is the build base; mobile is the planning layer

**Date**: 2026-05-14
**Status**: Accepted

**Context**: Owner uses both local Claude Code (desktop) and Claude mobile/web. Need a clean division of labor.

**Decision**:
- **Local Claude Code**: building, testing, deploying, autonomous chunk execution. Has filesystem, git, pnpm, uv.
- **Mobile Claude (web/app)**: strategy, memory file updates, research, application draft writing, planning future chunks.
- **GitHub** is the shared filesystem between them. Memory files in `bjc-portfolio` are the handoff.

**Consequences**:
- No upload/download dance for code
- Mobile sessions remain useful during commute / breaks
- All durable knowledge survives both surfaces

---

## ADR-010 — Apply when 2 of 3 projects demoable, not all 3

**Date**: 2026-05-14
**Status**: Accepted

**Context**: Waiting for "perfect" delays first contract by weeks.

**Decision**: Begin applications as soon as resume-builder v0.2 + bjc-eval v0.1 are live. bjc-mcp can be in-progress.

**Consequences**:
- Earlier income
- Project 3 becomes "in active development" talking point during interviews
- If first 5 applications fail, finish Project 3 before second wave

---

## ADR-011 — bjc-eval dataset is contamination-free; market this prominently

**Date**: 2026-05-14
**Status**: Accepted

**Context**: SWE-bench Verified (gold-standard SWE eval) has known contamination — Claude Opus 4.5 scored 80.9% on Verified vs. 45.9% on the contamination-free SWE-bench Pro.

**Decision**: bjc-eval's 50-item dataset is hand-authored, contamination-free, and publishable to Hugging Face under a permissive license. README prominently flags this as a differentiator.

**Consequences**:
- README headline: "Contamination-free dataset built from scratch"
- Owner must actually verify no item is reproduced from public benchmarks
- Optional future: publish dataset card on Hugging Face for citability

---

## ADR-012 — File creation tool fixture in bjc-eval tests uses varied score values

**Date**: 2026-05-14
**Status**: Accepted

**Context**: Initial test run failed 7/48. Root cause: perfect-agreement fixture used all-4s → zero variance → Cohen's κ mathematically undefined (0/0).

**Decision**: Fixtures spread scores across the 2–5 range with both judges identical. κ is now mathematically defined and tests verify correctness.

**Consequences**:
- All 48 tests pass
- Future fixture changes must preserve score variance
- Note this gotcha in CONTRIBUTING.md when written

---

## Decision queue (open, awaiting ADRs)

- Which domain for bjc-mcp-*?
- Hugging Face dataset publication timing for bjc-eval?
- Whether to use bjc-eval to score resume-builder's outputs (compounding portfolio narrative)?
- Rate negotiation floor — accept $80/hr or hold for $100/hr+?

---

## Updates log

- **2026-05-14**: File created with ADRs 001–012.
