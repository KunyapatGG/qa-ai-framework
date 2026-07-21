# Test Design Techniques

Reference for the `test-condition` skill. Formal, black-box techniques to derive conditions from requirements.

---

## 1. Equivalence Partitioning (EP)
Divide inputs into classes where the system behaves the same; test one value per class.
- Valid classes + invalid classes.
- Example: age field 18–65 → classes: <18, 18–65, >65.

## 2. Boundary Value Analysis (BVA)
Bugs cluster at edges. Test min-1, min, min+1, max-1, max, max+1.
- Range "orders over ฿500" → test 499.99, 500.00, 500.01.

## 3. Decision Table Testing
For combinations of conditions/rules. Each rule combination = one column.

| Condition | R1 | R2 | R3 | R4 |
|---|---|---|---|---|
| Member? | Y | Y | N | N |
| Order > ฿500? | Y | N | Y | N |
| **Action: 10% off** | ✅ | ❌ | ❌ | ❌ |

## 4. State Transition Testing
For status/workflow fields. Test valid transitions and, crucially, invalid ones.
- Order: `Cart → Placed → Paid → Fulfilled → Closed`; also `Placed → Cancelled`.
- Invalid: `Closed → Paid` must be rejected.

## 5. Use Case / Scenario Testing
End-to-end user journeys through the system.

## 6. Error Guessing / Exploratory
Experience-based; seed from `defect-patterns.md`.
- Empty, null, zero, negative, huge, special chars, duplicate submit, concurrent edit.

## 7. Pairwise / Combinatorial
When many parameters combine, test all pairs rather than full cartesian product.

---

## Technique selection guide
| Requirement shape | Technique |
|---|---|
| Numeric ranges / limits | BVA + EP |
| Multiple business rules combined | Decision Table |
| Status / lifecycle fields | State Transition |
| Many independent options | Pairwise |
| Complex user journey | Scenario |
| Legacy / unknown risk | Error Guessing |
