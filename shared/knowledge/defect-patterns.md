# Defect Patterns

Known failure modes, used by `risk-analysis` and `test-condition` (error-guessing) to predict where requirements will break.

---

## Requirement-level anti-patterns
- **Happy-path only** — no negative/error behavior specified.
- **Silent assumption** — a business rule assumed but never written.
- **Untestable adjective** — "fast", "user-friendly", "robust" with no metric.
- **Missing role model** — behavior differs by role but roles unstated.
- **Undefined empty/zero/null** — what happens with no data.
- **Timezone/locale blind** — dates, currency, tax not localized.

## Data & calculation
- Rounding errors in price/tax/discount.
- Off-by-one on boundaries (`>=` vs `>`).
- Integer overflow / precision loss on money (use decimal, not float).
- Currency/locale formatting mismatches.

## Concurrency & state
- Race condition on stock deduction → **oversell**.
- Double-submit → duplicate order / double charge.
- Stale-state edits (two users, same record).
- Invalid state transition allowed.

## Integration
- Timeout / partial failure of downstream service undefined.
- Retry without idempotency → duplicates.
- Silent failure (error swallowed, user sees success).

## Retail-specific
- Promotion stacking not intended but allowed.
- Expired coupon accepted.
- Refund exceeds original payment.
- Loyalty points double-awarded.
- Negative or zero-priced items.

## Security
- Missing authorization check on override actions.
- PII exposed in logs / responses.
- Injection via free-text fields.

---

## Usage
For each requirement, scan this list and ask: *"Does the requirement say what happens here?"* If not → finding + test condition + open question.
