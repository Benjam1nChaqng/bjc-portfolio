# 04 — Current Meta (2026)

> The "OP stuff." What's hot in AI engineering right now. What wows hiring teams at Anthropic, OpenAI, Google, Meta, and Microsoft. Updated continuously as the meta shifts.

## Meta ranking (highest signal first)

### Tier S — instant interview material

1. **Honest evals with measured κ scores.** A public repo with a real dataset, real rubric anchors, real Cohen's κ numbers reported honestly (including bad ones) is the single highest signal you can produce. AI labs spend 40% of their time on evals. Show you understand this.

2. **Inspect AI usage.** Anthropic's open-source eval framework. Using it (vs. rolling your own) signals "I read internal Anthropic blog posts." 90% of AI Trainer candidates have never heard of it.

3. **Multi-judge ensembles with bias mitigations.** Single-judge eval work is 2024-coded. Current meta is 3-judge ensembles (one from each major lab) with explicit bias mitigations: position randomization, verdict-balanced few-shot, self-consistency averaging.

4. **Custom MCP server.** Anthropic donated MCP to the Linux Foundation in Dec 2025. The ecosystem exploded. There are 10k+ public MCP servers as of mid-2026. Publishing a thoughtful one for a real domain you have data in (your GitHub, your calendar, your fitness data) is protocol-level signal.

### Tier A — strong differentiators

5. **Reproducible Hugging Face datasets.** Publishing your eval dataset as a versioned, citable HF dataset. CITED by other researchers if it's good.

6. **Trace-based agent debugging.** OpenTelemetry traces or LangSmith / Arize / Helicone observability of every agent run. "I instrumented my agent" beats "I shipped my agent."

7. **Adversarial agent-vs-agent setups.** Red-team agent that systematically tries to break the agent under test. Captures failure modes the developer didn't think of.

8. **Verdict-balanced few-shot calibration.** Most LLM judges are biased toward "5" because few-shot examples show only successes. Showing balanced examples across all score levels is a known mitigation that few people implement.

9. **Cost-aware inference routing.** Local models (Ollama / vLLM) for cheap tasks, frontier models for hard ones. Show you understand the cost curve.

10. **TDD with Inspect-style mocks.** Testing agent code without burning API credits. Mock the SDK, verify tool-choice contracts, validate Zod/Pydantic outputs.

### Tier B — table stakes (not differentiators, but required)

11. CI/CD with eval gating (block regressions > X%)
12. Conventional commits + CHANGELOG
13. Typed everything (TypeScript / Pydantic / Zod)
14. ≥80% test coverage on logic-heavy modules
15. README with metrics, demo link, and clear "what this is" up top

### Tier C — overrated in 2026 (do not over-invest)

- LangChain / LangGraph — heavy, often the wrong abstraction
- Pinecone / Weaviate vector DBs — pgvector + sqlite-vec are enough for portfolio scale
- Custom RAG implementations — only impressive if domain is novel and retrieval quality is measured
- ChromaDB tutorials — beginner signal
- Fancy frontends without backend depth

## Frameworks worth knowing (as of mid-2026)

- **Inspect AI** (Anthropic) — Tier S. The eval framework.
- **MCP SDK** (Python + TypeScript) — Tier S. The protocol.
- **Claude Agent SDK** — for agentic workflows in Claude-native stacks.
- **OpenAI Agents SDK** — released late 2025, growing fast.
- **Mastra** — TypeScript agent framework, getting traction in JS ecosystem.
- **LangGraph** — still dominant in enterprise. Heavy. Not exciting in 2026.
- **CrewAI** — multi-agent orchestration. Niche.

## Models that matter (mid-2026)

- **Claude Opus 4.7** — frontier reasoning, eval judge default
- **Claude Sonnet 4.6** — workhorse for cheaper agentic work
- **Claude Haiku 4.5** — fast/cheap for high-volume operations
- **GPT-5.2** — OpenAI frontier
- **Gemini 3 Pro** — Google frontier, strong on long-context
- **Llama 4 / DeepSeek V4** — local-runnable for cost-aware fallback

## Things hiring teams are tired of seeing

1. ChatGPT wrapper apps
2. Generic "AI assistant" projects without a domain
3. Vector DB tutorials reproduced as projects
4. Resumes that say "experience with LLMs" with no public artifacts
5. README files that don't show actual numbers
6. Demos that work in dev but the live URL is broken
7. Projects without tests
8. "Built with Cursor" listed as a skill (using AI to code is not a skill anymore — it's a baseline)

## Things hiring teams pay $150/hr for

1. Engineers who can author rubrics that produce κ ≥ 0.6 inter-rater agreement
2. Engineers who can debug *why* an agent is failing (traces, not vibes)
3. Engineers who can design evals before features (eval-driven development)
4. Engineers who recognize when a project should stop (taste)
5. Engineers who publish honest negative results (epistemic integrity)
6. Engineers who understand model behavior at the level of "this is a calibration issue" or "this is a tokenization edge case"

## Application-specific meta

### LinkedIn AI Labor Marketplace
- Apply within 48 hours of posting
- Custom cover-letter paragraph that names specific deliverables in your repo
- Government-ID verified profile (CLEAR / Persona)
- Headline format: "Software Engineer · [Specialization] · Building [project]"
- 1–2 line GitHub link in featured section

### Mercor
- AI interview is multi-stage. Practice with Claude as the interviewer first.
- Microsoft Edge or Safari only (Chrome breaks the recorder)
- Camera + mic permissions on, well-lit room
- Reference specific repo metrics in answers (κ scores, test count, deploy URLs)

### Handshake AI / Surge AI
- More structured intake. Send portfolio link in initial application.
- Domain expertise listing matters more than at Mercor.

## Updates log

- **2026-05-14**: Initial meta snapshot. Inspect AI = top signal. MCP ecosystem explosion. 3-judge ensembles are current standard. Local model routing emerging as differentiator.

(Append new entries to the bottom as the meta shifts. Date stamp everything.)
