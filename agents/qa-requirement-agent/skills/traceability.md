# Skill: Traceability

**Purpose:** Ensure every requirement traces backward to a source/need and forward to acceptance criteria and test conditions — no orphans, no gaps.

**Invoked when:** User asks about coverage/end-to-end; also runs as step 3d of the agent loop.

---

## Trace chain
```
Business need / Epic
        ↓
Requirement / User Story  ── links to → Jira key, Confluence spec
        ↓
Acceptance Criteria (AC-1..n)
        ↓
Test Conditions (TC-1..m)
        ↓
Test Cases / Test Coverage
```

## Procedure
1. Confirm the requirement links to a source (Epic, spec, ticket). Use `shared/tools/jira` / `shared/tools/confluence`. Source locations for the active project are listed in `projects/<PROJECT>/context/sources.md`.
2. Enumerate acceptance criteria; assign stable IDs (AC-1, AC-2, …).
3. Map each AC → one or more test conditions (from `test-condition` skill).
4. Detect:
   - **Orphan AC** — no test condition.
   - **Orphan condition** — tests something not in any AC (scope creep).
   - **Uncovered path** — negative/boundary path with no AC.
5. If a diff/PR is in scope, use `shared/tools/git` to check code touches the traced area.

## Output
- Traceability matrix: `AC → TC → status`.
- Gap list (uncovered ACs, missing source link, scope creep).
- Coverage %: covered ACs / total ACs.

## Matrix example
| AC | Description | Test Conditions | Status |
|----|-------------|-----------------|--------|
| AC-1 | Apply 10% member discount | TC-01, TC-02 | ✅ covered |
| AC-2 | Reject expired coupon | — | ❌ gap |
