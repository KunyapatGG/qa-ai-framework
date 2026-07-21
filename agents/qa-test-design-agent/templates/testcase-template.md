# Test Case — {TC_ID}

Concrete, executable test case derived from a test condition.

---

## Header
| Field | Value |
|---|---|
| **ID** | {TC_ID} |
| **Title** | {short descriptive title} |
| **Traces to** | {AC-x / requirement id} |
| **Type** | positive / negative / boundary / business-rule |
| **Priority** | High / Medium / Low |
| **Technique** | EP / BVA / Decision Table / State Transition / Scenario |

## Preconditions
- {state / data / role required before the test}

## Test data
| Field | Value |
|---|---|
| {input} | {value} |

## Steps
1. {action}
2. {action}
3. {action}

## Expected result
- {observable, verifiable outcome}

## Postconditions
- {resulting state, cleanup}

---

## Example — TC-02 (boundary)
| Field | Value |
|---|---|
| Title | Member discount not applied at exactly ฿500 |
| Traces to | AC-1 |
| Type | boundary |
| Technique | BVA |

**Preconditions:** Logged-in member with active membership.
**Test data:** Order subtotal = ฿500.00.
**Steps:** 1. Add items totaling ฿500.00. 2. Proceed to checkout.
**Expected result:** No discount applied (rule is "over ฿500", so ฿500.00 is excluded); total remains ฿500.00.
