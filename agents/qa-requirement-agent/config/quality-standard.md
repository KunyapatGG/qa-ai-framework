# Quality Standard

The rubric the QA Requirement Agent grades every requirement against. Based on INVEST + testability + business-rule coverage.

---

## 1. The INVEST checklist (for user stories)

| Letter | Criterion | Pass condition |
|---|---|---|
| **I** | Independent | Story can be built/tested without hidden dependency, or dependency is explicitly linked. |
| **N** | Negotiable | Describes intent, not a locked implementation. |
| **V** | Valuable | Clear user/business value stated. |
| **E** | Estimable | Enough detail for the team to size it. |
| **S** | Small | Fits in one sprint / one deliverable slice. |
| **T** | Testable | Acceptance criteria are concrete and verifiable. |

---

## 2. Acceptance-criteria quality

Every acceptance criterion must be:

- **Atomic** — one behavior per criterion.
- **Observable** — a tester can see pass/fail without reading the developer's mind.
- **Given/When/Then** or equivalently unambiguous structure.
- **Bounded** — inputs, ranges, and error states defined.

---

## 3. Completeness dimensions

A complete requirement covers:

- ✅ Happy path
- ✅ Alternate / negative paths
- ✅ Boundary & limit values
- ✅ Error handling & messaging
- ✅ Permissions / roles
- ✅ Data validation rules
- ✅ Non-functional needs (performance, security, availability) where relevant
- ✅ Business rules cited from `shared/knowledge/retail-business-rules.md` and the active project's `projects/<PROJECT>/knowledge/business-rules.md`

---

## 4. Scoring model

Score = weighted average, 0–100.

| Dimension | Weight |
|---|---|
| Clarity / no ambiguity | 25% |
| Completeness | 25% |
| Testability | 25% |
| Business-rule coverage | 15% |
| Traceability | 10% |

**Readiness thresholds**
- `READY`: score ≥ 85 **and** zero critical **and** zero unresolved major.
- `CONDITIONAL`: score 70–84, or majors that are resolvable with listed conditions.
- `NOT_READY`: score < 70, or any critical finding.

---

## 5. Definition of Ready (DoR)

A requirement is Ready when:

1. Value and user are stated.
2. Acceptance criteria are testable and complete.
3. Dependencies are identified.
4. Business rules referenced and confirmed.
5. No blocking open questions remain.
6. Test conditions can be derived for every acceptance criterion.
