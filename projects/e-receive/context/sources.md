# Sources — E-Receiving

> Where this project's requirements live, so agents (via `shared/tools/`) know where to fetch.
> Access reviewed: 2026-07-21 (Jira ✅ readable · Confluence ✅ readable · GitLab ❌ not yet accessible).

## Jira
- **Site / cloudId:** `makroo2o.atlassian.net` (cloudId `2b0d9d70-d695-49ab-9f84-d8ebd72d72fe`)
- **Project key(s):** `REV`
- **Releases:** ALL fix versions / releases are in scope (e.g. `30 July 2026`, and every other version on the project's Releases page).
- **Issue types in scope:** ALL — `Story`, `Task`, `Sub-task`, `Bug`.
- **Relevant JQL:**
  - Everything in project: `project = REV ORDER BY updated DESC`
  - Scoped to a release: `project = REV AND fixVersion = "<VERSION NAME>" ORDER BY status`
  - Requirements only (for a focused review): `project = REV AND issuetype in (Story, Task, Sub-task, Bug)`
- **Workflow statuses seen:** `To Do` → `REQ Writing` → `Reviewed` → `Coding` (Jira Software custom workflow).
- **Size (2026-07-21):** ~881 issues total, of which ~234 are Stories.
- **Release index (UI):** https://makroo2o.atlassian.net/projects/REV?selectedItem=com.atlassian.jira.jira-projects-plugin%3Arelease-page

## Confluence
- **Space key:** `HS`
- **Root page:** `E-Receiving` (pageId `2399305733`) — https://makroo2o.atlassian.net/wiki/spaces/HS/pages/2399305733/E-Receiving
- **Scope:** the ENTIRE page tree under the root page is in scope — no exclusions. Includes (non-exhaustive):
  - `E-Receiving` (BRD — background, objective, scope, functional requirements, business rules, API/integration)
  - `PRD in roadmap`, `Grooming session`, `Kickoff & plan E-claim`, `Team Workflow [DRAFT]`
  - `QA Document (E-Receiving) v.01` / `V02 - Draft version`
  - `Release DD-MM-2026` weekly pages + `E-Receiving - Technical Documents` (`System Overview`, `Release Note ...`)
  - `Postmortem ...`, onsite observations, business-performance metrics, how-to test-data pages
- **How to enumerate the tree:** start from pageId `2399305733`, walk descendants (depth ≥ 3).

## Git (optional — for traceability)
- **Repository:** https://gitlab.com/mango-engineering/e-receiving  — **READ-ONLY**, code only, never write.
- **Default base branch:** `<unconfirmed — ask before use>`
- **Status:** ⚠️ NOT accessible to agents yet — repo sits behind GitLab SAML SSO and no connector is wired up. Traceability-to-code (loop step 3d) must be done manually until access is arranged. To be revisited later.

## Notes
- **Access / permissions:** Atlassian (Jira `REV` + Confluence space `HS`) is readable via the connected Atlassian integration. GitLab is not — see above.
- **Known blind spots (agent is text-only — raise as open questions, never guess):**
  - Visual artifacts are NOT machine-readable: embedded diagrams (User Journey Flow), UI screenshots, the **Miro board** (`https://miro.com/app/board/uXjVJBXjdZg=/`) and the **Figma design** (`https://www.figma.com/design/glold0Kl3xF6Ydh5wUaNxG/E-Receiving-Design`). Requirements that live only in these will be missed.
  - The BRD root page is marked **In-Progress** (BRD review 2025-12-25, last edited 2026-01-06) while release notes run through Aug 2026 — the BRD may be **stale** vs. shipped behaviour. Treat conflicts as open questions.
- **Domain terms to capture in `knowledge/glossary.md`:** BOL, Load Manifest, GR, DC, Pallet, Distro No., Order No., RMS, SIM, WMOS, Mendix, TransferHub, invcInd, `E_RECEIVED`, H2H, MSP.
