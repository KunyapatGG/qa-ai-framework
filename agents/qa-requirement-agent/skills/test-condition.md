# Skill: Test Condition Derivation

**Purpose:** Turn acceptance criteria into concrete, testable conditions using formal test-design techniques.

**Invoked when:** User asks "can we test this" / "derive test conditions"; also runs as step 3e of the agent loop.

---

## Procedure
1. For each acceptance criterion, identify inputs, states, and expected outputs.
2. Apply techniques from `shared/knowledge/test-design-techniques.md`:
   - Equivalence Partitioning
   - Boundary Value Analysis
   - Decision Tables (for rule combinations)
   - State Transition (for status flows)
   - Error Guessing (seed from `shared/knowledge/defect-patterns.md`)
3. Generate conditions covering: positive, negative, boundary, business-rule.
4. Trace each condition back to its AC (`traces_to`).

## Output
- Test conditions list (schema: `shared/config/output-schema.md`).
- Optional draft cases via `agents/qa-test-design-agent/templates/testcase-template.md`.

## Coverage targets
- Every AC → ≥1 positive **and** ≥1 negative condition.
- Every numeric range → boundary conditions (min-1, min, max, max+1).
- Every rule combination → a decision-table row.
- Every status field → state-transition conditions (valid + invalid transitions).

## Example
**AC:** "Members get 10% off orders over ฿500."

| TC | Type | Condition | Expected |
|----|------|-----------|----------|
| TC-01 | positive | Member, order ฿600 | 10% discount applied |
| TC-02 | boundary | Member, order exactly ฿500 | No discount (rule is *over* 500) |
| TC-03 | boundary | Member, order ฿500.01 | 10% discount applied |
| TC-04 | negative | Non-member, order ฿600 | No discount |
| TC-05 | negative | Member, expired membership | No discount |
