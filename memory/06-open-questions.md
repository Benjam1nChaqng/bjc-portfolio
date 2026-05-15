# 06 — Open Questions

> Research queue. Open decisions. Things to figure out. Move resolved items to `03-decisions.md` as ADRs.

---

## High priority (blocks shipping)

### Q1 — Vercel BLOB_READ_WRITE_TOKEN deploy issue
- **Symptom**: resume-builder deploy fails on Vercel due to `BLOB_READ_WRITE_TOKEN` not being read
- **Hypotheses**:
  1. Store-namespaced env var name (e.g., `RESUME_PDFS_READ_WRITE_TOKEN`) — Vercel created a namespaced name when the Blob store was provisioned
  2. Env var propagation delay (rare, but possible if recently added)
  3. Vercel project not linked to the Blob store correctly
- **Resolution path**: 
  1. Check Vercel dashboard → project → Storage tab → confirm Blob store is linked
  2. Check Settings → Environment Variables → see actual var names
  3. Update code to read the correct env var name OR rename in Vercel
- **Owner**: blocks Loom recording for resume-builder

### Q2 — Domain choice for bjc-mcp-*
- **Context**: Project 3 in the portfolio is a custom MCP server. Need to pick a domain.
- **Criteria**:
  1. Owner has real data already (no setup friction)
  2. Solves a real annoyance owner currently feels
  3. Ship in ~20 hours total
  4. Demo-able as a Loom or screen recording in <2 minutes
- **Candidates**:
  - **`bjc-mcp-github-personal`** — owner's commits, PRs, issues across personal repos. Great for "tell me what I worked on this week" queries. Demo-friendly.
  - **`bjc-mcp-calendar`** — calendar + tasks. Useful for daily standups. Less novel.
  - **`bjc-mcp-strava`** — fitness/running data. Personal and visual. Niche.
  - **`bjc-mcp-files`** — local file search. Useful but crowded (many existing implementations).
- **Recommendation (provisional)**: `bjc-mcp-github-personal` — best demo narrative + matches owner's developer identity
- **Decision deadline**: when resume-builder v0.2 ships

---

## Medium priority (affects portfolio narrative)

### Q3 — Should resume-builder use bjc-eval to score its own outputs?
- **Idea**: bjc-eval scores the bullet-tailoring agent's outputs. Creates a compounding portfolio narrative ("Project 1 and Project 2 use each other").
- **Pro**: massive hiring signal — "I built the eval harness and used it to validate my own agent"
- **Con**: scope creep. Adds work to both projects.
- **Tentative decision**: Do this ONLY after both projects hit v0.1. Add as a Loom segment showing the integration, not as a feature of either project.
- **Decision deadline**: when bjc-eval v0.1 ships

### Q4 — Hugging Face dataset publication timing
- **Idea**: Publish bjc-eval's 50-item dataset as a versioned, citable Hugging Face dataset.
- **Pro**: Tier A signal per `04-meta.md`. Citability. Cleaner README.
- **Con**: ~3 hours of work for dataset card, licensing, formatting.
- **Tentative decision**: Publish AFTER first contract is landed OR if first 5 applications fail (then it becomes a leverage move).

### Q5 — Loom recording strategy
- **Options**:
  - Phone screen recording with voiceover (lower quality, faster)
  - Desktop screen recording with mic (higher quality, slower)
  - Loom-native browser extension (medium effort, good quality)
- **Tentative decision**: Loom browser extension on desktop. Owner records all 3 project Looms in one ~2-hour session.

---

## Low priority (nice to have / parking lot)

### Q6 — GitHub username rename target
- **Current**: `Benjam1nChaqng`
- **Candidates**: `benjaminchang`, `bjchang`, `benjamin-chang`, `bjc-dev`
- **Constraint**: must be available; should match bjc-platform branding
- **Decision deadline**: before first application

### Q7 — Domain purchase for portfolio landing page
- **Options**: `bjchang.dev`, `benjamin.engineering`, `bjc-platform.com`
- **Need**: probably no — GitHub Pages + `bjc-portfolio/README.md` is enough for v1
- **Decision deadline**: skip until needed

### Q8 — Rate negotiation floor: $80 or $100?
- **Current**: $80 (per `05-applications.md`)
- **Reconsider**: if first 3 offers all come in at $60–$70, may need to drop floor to $70 short-term, then raise after first contract is on resume
- **Decision deadline**: after first 3 offers received

### Q9 — Adversarial red-team agent for bjc-eval v0.2
- **Idea**: Build a red-team agent that systematically tries to fool the judge ensemble. Captures failure modes. Massive signal.
- **Scope**: ~10–15 hours. Out of v0.1 scope.
- **Decision**: parking lot for v0.2 only if hiring momentum stalls

### Q10 — Local model inference (Ollama) integration
- **Idea**: Add Llama 4 or DeepSeek V4 as a 4th judge for cost-aware routing demo.
- **Pro**: Tier A meta signal (cost-aware routing).
- **Con**: Adds operational complexity. Out of v0.1 scope.
- **Decision**: parking lot for v0.2

---

## Resolved (move to `03-decisions.md` as ADRs when promoted)

*(empty — populate as questions resolve)*

---

## Updates log

- **2026-05-14**: File created with Q1–Q10. No questions resolved yet.
