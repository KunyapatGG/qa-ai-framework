# Open Questions — {REQUIREMENT_ID}

Clarifying questions raised during review. Each question names an owner, states why it matters, and whether it blocks readiness.

---

## Format

### Q-{n}: {short title}
- **To:** {PO / BA / Dev / Design / Data}
- **Blocking:** {Yes / No}
- **Context:** {quote or reference from the requirement}
- **Question:** {the precise, answerable question}
- **Why it matters:** {impact on build/test if unanswered}
- **Suggested options (if any):** {A / B / C}

---

## Example

### Q-01: Do member discounts stack with promo codes?
- **To:** PO
- **Blocking:** Yes
- **Context:** AC-2 says "members get 10% off"; §Promotions mentions a "SUMMER" code.
- **Question:** When a member uses a promo code, do both discounts apply, or only the larger one?
- **Why it matters:** Determines the discount calculation and creates a critical pricing-defect risk if wrong.
- **Suggested options:** (A) Do not stack, apply larger. (B) Stack additively. (C) Stack multiplicatively.

---

## Batch summary (paste into Jira/Confluence)

| ID | To | Blocking | Question |
|----|----|----------|----------|
| Q-01 | PO | Yes | {question} |
| Q-02 | BA | No | {question} |
