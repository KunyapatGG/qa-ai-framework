# Tool: API

Generic connector for programmatic access — fetching requirements from custom systems, or emitting an agent's structured output to downstream tooling. Shared by all agents in the framework.

---

## Purpose
- Pull requirement data from systems without a dedicated connector (test-management tools, internal APIs).
- Push the agent's machine-readable output (`shared/config/output-schema.md` JSON) to CI, dashboards, or a test-management system.

## Contract
- **Input:** a requirement payload (id, title, text, acceptance_criteria[]).
- **Output:** the canonical JSON from `shared/config/output-schema.md`.

### Example input
```json
{
  "requirement_id": "REQ-1234",
  "title": "Member discount at checkout",
  "text": "...",
  "acceptance_criteria": ["Members get 10% off orders over ฿500", "..."]
}
```

### Example output
See the canonical shape in `shared/config/output-schema.md` (verdict, findings, risks, open_questions, test_conditions, traceability).

## Usage rules
- Authenticate via environment-provided secrets; **never** hard-code or log credentials (`shared/config/guardrails.md`).
- Validate all incoming payloads before analysis.
- Respect rate limits and timeouts; surface partial failures rather than silently dropping data.

## Status
Placeholder scaffold — wire up to your specific endpoints/auth. Define base URL, auth method, and endpoints here when integrating.
