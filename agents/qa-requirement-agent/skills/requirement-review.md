# Skill: Requirement Review

**Purpose:** Assess structure and completeness of a requirement against the quality standard.

**Invoked when:** User asks to "review", "check", or "assess" a requirement; also runs as step 3a of the agent loop.

---

## Inputs
- Requirement text (story / PRD / AC)
- Optional linked context (Jira/Confluence/Git)

## Procedure

1. **Parse the requirement** into: user/value, action, acceptance criteria, constraints.
2. **Run INVEST** (`agents/qa-requirement-agent/config/quality-standard.md §1`). Record any letter that fails.
3. **Check completeness dimensions** (`§3`): happy path, negative paths, boundaries, errors, roles, validation, NFRs, business rules.
4. **Map each acceptance criterion** to the atomic/observable/bounded test (`§2`).
5. **Flag findings** with severity + category + evidence + recommendation.
6. **Compute partial score** for clarity & completeness dimensions.

## Output
- List of findings (schema: `shared/config/output-schema.md`).
- Completeness matrix: which dimensions are ✅ / ⚠️ / ❌.
- Handoff note to `ambiguity-check` and `test-condition`.

## Checklist
- [ ] Value & user identified
- [ ] Every AC atomic and observable
- [ ] Negative & boundary paths present
- [ ] Error handling defined
- [ ] Roles/permissions defined
- [ ] Business rules cited and confirmed
- [ ] Dependencies identified
