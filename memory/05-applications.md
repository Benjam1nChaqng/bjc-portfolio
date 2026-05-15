# 05 — Applications

> Job application pipeline. Update on every action. Append-only on outcomes.

## Pre-application gates (must clear before applying anywhere)

- [ ] resume-builder v0.2 deployed to public URL
- [ ] resume-builder 90-second Loom recorded
- [ ] bjc-eval v0.1 public repo with measured κ numbers
- [ ] LinkedIn government-ID verification complete (CLEAR or Persona)
- [ ] LinkedIn headline updated: "Software Engineer · LLM Evaluation & Agent Systems · Building bjc-platform"
- [ ] LinkedIn featured section: github.com/[username]/bjc-portfolio + Loom links
- [ ] GitHub username renamed from `Benjam1nChaqng` to clean handle
- [ ] Portfolio README polished (bjc-portfolio top-level)
- [ ] Resume PDF current and tailored for AI Trainer / LLM Eval roles

**Apply gate**: 2 of 3 projects demoable AND all 8 checkboxes above complete.

---

## Target platforms (ranked by leverage)

### LinkedIn AI Labor Marketplace
- **Best for**: $100–$150/hr Software Engineering AI Trainer roles
- **Strategy**: apply within 48 hours of listing posting
- **Custom paragraph**: name 2 specific deliverables from `bjc-eval` README
- **Daily action**: 5-minute scan of new listings tagged "AI Trainer" / "LLM" / "Software Engineering AI"

### Mercor
- **Best for**: LLM Evaluation Specialist roles ($50–$100/hr)
- **Process**: AI interview, multi-stage
- **Browser**: Microsoft Edge or Safari only (Chrome breaks the recorder)
- **Prep**: practice mock interview with Claude as interviewer first
- **Reference**: cite specific repo metrics during answers (κ score, test count, deploy URL)

### Handshake AI
- **Best for**: coding-focused LLM trainer roles ($50–$80/hr)
- **Process**: structured intake; portfolio link required in initial application
- **Strategy**: lead with `bjc-eval` since it's the direct domain match

### Surge AI
- **Best for**: technical labeler / evaluator roles
- **Process**: skills test + portfolio review
- **Strategy**: same as Handshake — `bjc-eval` first

### Blocked
- **Outlier (Scale AI)**: California Working Location Policy. AB5 / Prop 22. Do not apply.

---

## Application log

> Format: `YYYY-MM-DD | platform | role | rate | status | notes`

*(empty — no applications submitted yet)*

---

## Listings of interest (watch list)

> Format: `YYYY-MM-DD captured | platform | role | rate | URL or ID | notes`

*(empty — populate when listings are seen and applications gated)*

---

## Interview prep notes

- **Common technical questions to expect**:
  - "How do you measure if an LLM judge is reliable?" → Cohen's κ, Krippendorff's α, judge-vs-human comparison
  - "What biases does LLM-as-judge have?" → position bias, verdict bias, self-preference, length bias. Reference CALM (Ye et al., ICLR 2025).
  - "How would you build a rubric?" → worked anchors at every score level, evidence-first reasoning, dimension orthogonality
  - "What's wrong with SWE-bench?" → known contamination on Verified split; reference 80.9% (Verified) vs 45.9% (Pro) for Opus 4.5
- **Common behavioral questions**:
  - "Tell me about a project you shipped" → walk through bjc-eval architecture decisions
  - "What's a technical decision you regret?" → real one from the build, with honest reflection
- **Closing questions to ask**:
  - "What does the eval workflow look like inside the team?"
  - "How do you measure annotator quality on this contract?"

---

## Rate negotiation policy

- **Floor**: $80/hr (per ADR-007 strategy doc reference)
- **First counter-offer if offered $50–$70/hr**: politely decline with reference to portfolio depth; ask if there's a more senior tier
- **Soft yes range**: $80–$100/hr
- **Hard yes range**: $100/hr+
- **Negotiation lever**: portfolio link with measured κ numbers + production deploy URLs

---

## Updates log

- **2026-05-14**: File created. No applications submitted yet. All pre-gates open.
