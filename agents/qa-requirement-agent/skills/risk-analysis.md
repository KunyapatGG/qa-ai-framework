# Skill: Risk Analysis

**Purpose:** Identify business and technical risks a requirement introduces, and where testing effort should concentrate.

**Invoked when:** User asks about risks; also runs as step 3c of the agent loop.

---

## Risk dimensions
- **Business risk** — revenue, customer trust, compliance, brand.
- **Technical risk** — integrations, data migration, concurrency, performance.
- **Operational risk** — rollout, rollback, support load.
- **Data risk** — PII, financial accuracy, inventory integrity.

## Procedure
1. Identify what could go wrong for each acceptance criterion.
2. Cross-reference `shared/knowledge/defect-patterns.md` (and the active project's `projects/<PROJECT>/knowledge/defect-patterns.md`) for known failure modes.
3. Cross-reference `shared/knowledge/retail-business-rules.md` and `projects/<PROJECT>/knowledge/business-rules.md` for high-stakes rules (pricing, promotions, stock, payments).
4. Rate each risk: **Likelihood** (H/M/L) × **Impact** (H/M/L).
5. Recommend mitigations and priority test areas.

## Risk scoring

| Impact \ Likelihood | Low | Med | High |
|---|---|---|---|
| **High** | Medium | High | Critical |
| **Med** | Low | Medium | High |
| **Low** | Low | Low | Medium |

## Output
- Risk register (id, area, likelihood, impact, mitigation).
- "Test-here-first" list of highest-priority areas.

## Retail hotspots to always check
- Pricing & discount calculation
- Promotion stacking / eligibility
- Inventory / stock deduction & oversell
- Payment & refund flows
- Loyalty points accrual/redemption
- Tax / receipt correctness
