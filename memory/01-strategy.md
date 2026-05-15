# 01 — Strategy

> The big picture. Why we're building this. What winning looks like.

## North star

Land **$100–$150/hr AI Trainer / LLM Evaluation contract roles** within 60–90 days via a portfolio of 2–3 deep, focused AI projects that demonstrate platform-level engineering thinking.

## Target roles (ranked by leverage)

| Role | Rate | Platform | Match strength |
|------|------|----------|----------------|
| Software Engineering AI Trainer | $100/hr | LinkedIn AI Labor Marketplace | **Strong** — direct domain match |
| LLM Evaluation Specialist | $50–$100/hr | Mercor | **Strong** — bjc-eval is the credential |
| Coding-focused LLM trainer | $50–$80/hr | Handshake AI / Surge AI | Strong |
| Computer & Information Systems AI Trainer | $100–$150/hr | LinkedIn | Stretch — needs 10+ yrs enterprise IT |
| Excel — IT/Enterprise Software | $90–$100/hr | LinkedIn | Skip — domain mismatch |

**Outlier (Scale AI): permanently blocked** by California Working Location Policy (AB5 / Prop 22 issue). Do not waste time applying.

## Win condition

Two-part definition of "won":

1. **Booked**: At least one contract role signed at ≥ $80/hr by day 90.
2. **Compounding**: Each completed project visibly improves the next. By end of Project 3, building Project 4 is half as much work as Project 1 was.

## Project pipeline (this is the spine of everything)

### Project 1: `resume-builder` — agentic Next.js app
- **Status**: v0.2 in progress (Chunks 7–8 mid-build as of 2026-05-14)
- **Stops at**: v0.2 (JD scraping + bullet tailoring functional). No grinding to v1.0.
- **Demonstrates**: agentic system design, multi-pass LLM workflows, TDD discipline, real deploy
- **Demo asset**: 90-second Loom walking through import → tailor → diff
- **Time remaining**: ~5–8 hours after Chunks 7/8 land (UI wiring + Loom + README polish)

### Project 2: `bjc-eval` — LLM evaluation harness
- **Status**: Spec written (see `bjc-eval/PRODUCT.md`). Build not yet started.
- **v0.1 scope**: 50 examples / 3 categories / 3 judges (Opus 4.7 + GPT-5.2 + Gemini 3 Pro) / 3 rubric dimensions / 20-item human ground truth
- **Demonstrates**: rubric design, multi-judge ensembles, inter-rater reliability, eval engineering — **this IS the AI Trainer job**
- **Stops at**: v0.1
- **Time**: ~25–40 hours
- **Domain**: software engineering (matches owner's skills + target roles)
- **Why it's the highest-leverage project**: every preferred qualification on the LinkedIn $100/hr Software Engineering AI Trainer listing maps directly to a deliverable in this repo. The README is the application.

### Project 3: `bjc-mcp-*` — custom MCP server
- **Status**: Not started. Domain TBD.
- **Likely domain**: personal-data MCP — owner's GitHub commits, calendar, Strava, or similar. Real data the owner already has access to.
- **Demonstrates**: protocol-level AI engineering, integration depth, the post-2025 MCP ecosystem fluency
- **Time**: ~15–25 hours

### Optional Project 4: `bjc-traces` or similar observability layer
- **Decision**: only build if pipeline doesn't land a contract by day 60. Otherwise skip.

## Application strategy

**Apply when 2 of 3 projects are live and demoable**, not all 3. Waiting for "perfect" is the failure mode.

Trigger conditions to apply:
- ✅ resume-builder v0.2 live URL + Loom + clean README
- ✅ bjc-eval v0.1 live repo + measured κ numbers + clean README
- ✅ LinkedIn government-ID verification complete (CLEAR or Persona)
- ✅ LinkedIn headline updated: "Software Engineer · LLM Evaluation & Agent Systems · Building bjc-platform"

Apply to **3–5 fresh listings within 48 hours of posting** on LinkedIn AI Labor Marketplace. Older listings = lower hit rate.

In parallel: book Mercor AI interview (Microsoft Edge or Safari only; practice with Claude as interviewer first).

## What this strategy is NOT

- **NOT building one monolithic "everything app."** Junior trap. Portfolio unity comes from shared *architecture* (`bjc-platform` ecosystem), not packaging.
- **NOT grinding each project to v1.0.** Each project stops at the version that demonstrates the skill. Polish goes into README + Loom, not features.
- **NOT chasing every domain.** Software engineering is the lane. Don't dilute by adding finance / healthcare / legal evaluation projects.
- **NOT optimizing for end users.** These are *portfolio pieces*. Hiring teams click the live URL once, read the README, watch the Loom, decide. They never use the actual product.

## Anti-patterns to refuse

1. Adding more features to resume-builder past v0.2
2. Starting Project 2 before resume-builder v0.2 is demoable
3. Inflating benchmark numbers in any README
4. Building features without tests
5. Pushing without verifying CI passes
6. Letting Claude Code go autonomous without memory file grounding
7. Accepting < $80/hr contracts (negotiate up or pass)

## Time budget

- Resume-builder v0.2 wrap-up: 8 hours
- bjc-eval v0.1 build: 35 hours
- bjc-mcp build: 20 hours
- Application + Loom + README polish: 10 hours total
- **Total to first paid contract: ~75 hours of focused work**

At 15 hours/week (evenings + weekends), that's 5 weeks of build → start applications → 2–4 weeks of application/interview cycle → contract by week 9.

## Updates log

- **2026-05-14**: Strategy created. Resume-builder Chunks 7–8 in autonomous build. bjc-eval spec written. Pivot from "everything app" framing to platform ecosystem framing.
