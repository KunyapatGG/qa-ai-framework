# Glossary

Shared vocabulary. The agent resolves business terms here before analysis; unknown terms become open questions rather than guesses.

> Extend this with your organization's real terms and definitions.

---

## QA / process terms
| Term | Definition |
|---|---|
| AC | Acceptance Criterion — a testable pass/fail condition of a requirement. |
| DoR | Definition of Ready — bar a requirement must meet before development. |
| DoD | Definition of Done — bar a work item must meet before it's complete. |
| Test Condition | A specific thing to verify, derived from an AC. |
| Test Case | Concrete steps + data + expected result implementing a condition. |
| Traceability | The linkage from need → requirement → AC → test. |
| BVA / EP | Boundary Value Analysis / Equivalence Partitioning (test techniques). |
| NFR | Non-Functional Requirement (performance, security, availability, etc.). |

## Retail / business terms (examples — confirm locally)
| Term | Definition |
|---|---|
| SKU | Stock Keeping Unit — unique product identifier. |
| POS | Point of Sale — checkout system. |
| Basket / Cart | Collection of items pending purchase. |
| Line item | A single product entry within an order. |
| Split tender | Paying one order with multiple payment methods. |
| Oversell | Selling more units than are in stock. |
| Void | Cancelling a transaction line or sale before settlement. |
| Override | Manual change (price/discount) requiring elevated permission. |
| Accrual | Earning of loyalty points. |
| Redemption | Spending of loyalty points. |
| Stacking | Applying more than one promotion/discount together. |

---

## Rule
If a requirement uses a term not defined here **and** its meaning affects behavior, the agent must raise an open question and (once confirmed) add it here.
