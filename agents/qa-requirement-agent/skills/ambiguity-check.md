# Skill: Ambiguity Check

**Purpose:** Detect language that can be interpreted more than one way, so dev and QA don't diverge.

**Invoked when:** User asks "is this clear/ambiguous"; also runs as step 3b of the agent loop.

---

## Ambiguity triggers (flag these)

| Category | Example phrases | Why risky |
|---|---|---|
| Vague quantifiers | "some", "few", "many", "several" | No testable threshold |
| Weak verbs | "handle", "support", "process", "manage" | Behavior undefined |
| Unbounded ranges | "large file", "fast", "quickly", "as needed" | No limit to test |
| Implicit actor | "it should", "the system will" | Who/what triggers? |
| Undefined terms | domain words not in glossary | Divergent meaning |
| Optional-sounding | "should ideally", "if possible", "etc." | Is it required? |
| Pronoun ambiguity | "it", "this", "they" with unclear referent | Wrong target |
| Missing negatives | only happy path stated | Error path undefined |

## Procedure
1. Scan requirement text against trigger table.
2. For each hit: quote it, name the interpretations, propose the clarifying question.
3. Resolve terms against the active project's `projects/<PROJECT>/knowledge/glossary.md` (falling back to `shared/knowledge/glossary.md`); if absent, flag + add to open questions.
4. Assign severity: an ambiguity on a business-critical rule = `critical`.

## Output
- List of ambiguities with: quote → possible meanings → recommended wording.
- Open questions for the PO/BA (feed `agents/qa-requirement-agent/templates/question-template.md`).

## Rewrite guidance
Prefer measurable rewrites:
- ❌ "Search should be fast."
- ✅ "Search results return within 2s for up to 10,000 SKUs."
