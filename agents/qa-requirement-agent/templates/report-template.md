# Requirement Review Report — {REQUIREMENT_ID}

**Title:** {TITLE}
**Reviewed:** {DATE}
**Source:** {JIRA_KEY / CONFLUENCE_LINK / inline}

---

## 1. Verdict

> **{READY | CONDITIONAL | NOT_READY}** — Quality score: **{SCORE}/100**

{One-paragraph summary of the state of this requirement.}

### Top blockers
1. {blocker — owner}
2. {blocker — owner}
3. {blocker — owner}

---

## 2. Findings

| ID | Severity | Category | Location | Finding | Recommendation |
|----|----------|----------|----------|---------|----------------|
| F-01 | critical | completeness | AC-2 | {statement} | {fix} |
| F-02 | major | ambiguity | §Scope | {statement} | {fix} |

*(Sorted critical → info.)*

---

## 3. Completeness matrix

| Dimension | Status |
|---|---|
| Happy path | ✅ / ⚠️ / ❌ |
| Negative paths | |
| Boundaries | |
| Error handling | |
| Roles/permissions | |
| Data validation | |
| NFRs | |
| Business rules | |

---

## 4. Risks

| ID | Area | Likelihood | Impact | Rating | Mitigation |
|----|------|-----------|--------|--------|-----------|
| R-01 | {area} | H/M/L | H/M/L | {rating} | {mitigation} |

---

## 5. Open questions

| ID | To | Question | Blocking? |
|----|----|----------|-----------|
| Q-01 | PO | {question} | Yes/No |

---

## 6. Suggested test conditions

| TC | Type | Condition | Traces to |
|----|------|-----------|-----------|
| TC-01 | positive | {condition} | AC-1 |
| TC-02 | boundary | {condition} | AC-1 |
| TC-03 | negative | {condition} | AC-2 |

---

## 7. Traceability

- **Source link:** {link / ❌ missing}
- **Acceptance criteria:** {n}
- **Covered by conditions:** {m} ({coverage %})
- **Gaps:** {list}

---

## 8. Next action
{e.g., "PO to resolve Q-01 and Q-03; then re-run readiness-review."}
