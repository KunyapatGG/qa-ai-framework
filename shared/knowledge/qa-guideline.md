# QA Guideline

General QA principles this agent operates by. Reference material for all skills.

---

## Core principles (ISTQB-aligned)
1. **Testing shows presence of defects**, not their absence.
2. **Exhaustive testing is impossible** — prioritize by risk.
3. **Early testing saves cost** — reviewing requirements is the earliest, cheapest defect-finding activity. *(This agent's whole reason to exist.)*
4. **Defects cluster** — a few modules hold most defects (see `defect-patterns.md`).
5. **Beware the pesticide paradox** — vary test conditions over time.
6. **Testing is context-dependent** — retail POS ≠ e-commerce ≠ back office.
7. **Absence-of-errors fallacy** — a bug-free build that doesn't meet the need still fails.

---

## Shift-left mindset
Defects found in requirements cost ~1x to fix; in production ~100x. Every ambiguity resolved before a line of code is written is the highest-ROI QA action.

---

## What "good" looks like
- Requirements are testable, unambiguous, traceable.
- Every business rule has an owner and a source.
- Negative and boundary behavior is defined, not assumed.
- Non-functional expectations (performance, security, availability) are explicit where they matter.

---

## Review etiquette
- Critique the requirement, not the author.
- Every finding carries a recommendation.
- Rank by risk; lead with blockers.
- Ask questions rather than assume intent.
