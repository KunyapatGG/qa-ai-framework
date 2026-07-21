# Output Schema

Defines the structured shape of every agent response (framework-wide contract). Human-readable reports render from each agent's report template (e.g. `agents/qa-requirement-agent/templates/report-template.md`); this file defines the underlying data contract.

---

## Severity levels

| Level | Meaning | Blocks readiness? |
|---|---|---|
| `critical` | Requirement cannot be built or tested correctly as written. | Yes |
| `major` | Significant gap/ambiguity; likely defect or rework. | Conditional |
| `minor` | Small clarity/quality issue. | No |
| `info` | Observation or suggestion. | No |

---

## Verdict values

- `READY` — clear, complete, testable. No critical, no unresolved major.
- `CONDITIONAL` — READY once listed conditions are met.
- `NOT_READY` — one or more critical findings, or too many unresolved majors.

---

## Canonical JSON shape

```json
{
  "requirement_id": "JIRA-1234 | confluence:pageId | inline",
  "project": "e-receive | inventory | ...",
  "title": "string",
  "verdict": "READY | CONDITIONAL | NOT_READY",
  "quality_score": 0,
  "summary": "string",
  "findings": [
    {
      "id": "F-01",
      "severity": "critical | major | minor | info",
      "category": "completeness | ambiguity | testability | risk | traceability",
      "location": "AC-3 | section | field",
      "statement": "what is wrong",
      "evidence": "quote from requirement",
      "recommendation": "what to do"
    }
  ],
  "risks": [
    { "id": "R-01", "area": "string", "likelihood": "H|M|L", "impact": "H|M|L", "note": "string" }
  ],
  "open_questions": [
    { "id": "Q-01", "to": "PO | BA | Dev | Design", "question": "string", "blocking": true }
  ],
  "test_conditions": [
    { "id": "TC-01", "type": "positive|negative|boundary|business-rule", "condition": "string", "traces_to": "AC-x" }
  ],
  "traceability": {
    "source": "link",
    "acceptance_criteria_count": 0,
    "covered_by_conditions": 0,
    "gaps": ["string"]
  }
}
```

---

## Rendering rules

- Always emit the **human-readable report** (via template) first.
- Include the JSON block only when the caller/tooling requests machine output.
- Sort findings by severity (critical → info), then by location.
- Every `open_question` marked `blocking: true` must be reflected in the verdict.
- Set `project` to the active project's folder name under `projects/`.
