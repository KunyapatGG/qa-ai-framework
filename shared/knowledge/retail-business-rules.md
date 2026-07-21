# Retail Business Rules

Domain rules the agent uses to judge completeness and risk. **These are starter examples — replace with your organization's confirmed rules.** Never treat an unconfirmed rule as fact; raise a question instead.

> ⚠️ Placeholder values. Confirm every threshold with the Product Owner before treating it as a rule.

---

## 1. Pricing & discounts
- Prices are stored and displayed in the store's local currency (e.g., THB ฿), tax handling per local regulation.
- Discounts apply to net price unless stated otherwise.
- Discount stacking rules must be explicit — default assumption: **discounts do not stack**.
- Rounding rule must be defined (e.g., round to 2 decimals, half-up).

## 2. Promotions
- Each promotion has: eligibility, start/end datetime, channel scope, and stacking rule.
- Expired or not-yet-active promotions must be rejected.
- Promotion + coupon interaction must be defined.

## 3. Inventory / stock
- Stock is deducted at a defined commit point (cart vs. payment vs. fulfillment) — must be explicit.
- **Oversell** (selling more than available) is a critical defect area.
- Negative stock must never be silently allowed.
- Reserved vs. available stock must be distinguished.

## 4. Payment & refund
- Supported payment methods must be enumerated.
- Partial payment / split tender rules defined.
- Refunds cannot exceed the paid amount.
- Idempotency required — a double-submit must not double-charge.

## 5. Loyalty / membership
- Points accrual rate and redemption rate defined.
- Membership expiry affects eligibility.
- Points must not go negative.

## 6. Tax & receipt
- Tax calculation and rounding must match legal requirements.
- Receipt totals must reconcile: sum(line items) − discounts + tax = total.

## 7. Roles & permissions
- Cashier, supervisor, manager, admin have distinct capabilities.
- Overrides (price, discount, void) require elevated role + audit trail.

## 8. Data & privacy
- Customer PII must be protected; masking rules for display.
- Audit trail required for financial and inventory-affecting actions.

---

## How the agent uses this file
- During `requirement-review`: check that relevant rules are addressed.
- During `risk-analysis`: flag high-stakes areas (pricing, stock, payment).
- During `ambiguity-check`: any rule referenced but not defined → open question.
