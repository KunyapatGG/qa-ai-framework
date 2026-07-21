# Skill: Readiness Review

**Purpose:** Produce the final verdict — is this requirement ready for development and testing?

**Invoked when:** User asks "is this ready"; also the final step (6) of the agent loop.

---

## Procedure
1. Ensure the full analysis loop has run (requirement-review, ambiguity-check, risk-analysis, traceability, test-condition). If not, run the missing skills first.
2. Aggregate all findings and open questions.
3. Apply the Definition of Ready (`agents/qa-requirement-agent/config/quality-standard.md §5`).
4. Compute the quality score (`§4`).
5. Determine verdict using thresholds:
   - `READY` — score ≥ 85, zero critical, zero unresolved major, zero blocking questions.
   - `CONDITIONAL` — resolvable with a listed set of conditions.
   - `NOT_READY` — any critical, or score < 70, or missing inputs.
6. Emit the top blockers, ranked.

## Output
- Verdict + score.
- DoR checklist with pass/fail per item.
- Ranked blocker list with owners.
- Recommended next action (e.g., "PO to answer Q-01, Q-03, then re-review").

## DoR checklist (rendered)
- [ ] Value & user stated
- [ ] Acceptance criteria testable & complete
- [ ] Dependencies identified
- [ ] Business rules referenced & confirmed
- [ ] No blocking open questions
- [ ] Test conditions derivable for every AC

> Rule: if any box is unchecked and its finding is critical → `NOT_READY`.
