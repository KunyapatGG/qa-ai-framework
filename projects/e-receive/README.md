# Project: E-Receiving

> Domain knowledge for the E-Receiving system. Agents load `shared/` + this folder
> when the active project is `e-receive`. Requirement sources are in `context/sources.md`.

---

## Overview
- **Slug:** `e-receive` (value used in the `project` output field; Jira key `REV`)
- **System / scope** (summarised from Jira project `REV` — 36 Epics):
  E-Receiving is a goods-receiving app/platform for store & warehouse receivers (GR) who
  scan barcodes (pallet / item) to receive goods, then push receiving data to the back-end
  systems (RMS → SIM). Scope from Jira covers:
  - **Core receiving:** Shipment, Scan Barcode, Receiving Items, Search, Over-Receiving
    (REV-1, 24, 25, 70, 159)
  - **Integration / E2E:** External System, E2E Integration, MSP, Kafka sync, RMS retry
    cronjob (REV-27, 124, 844, 909, 907, 760)
  - **Claim journey:** Pre-claim, E-claim, Interim-claim report — short / damaged / poor
    quality auto-submit to claim center (REV-190, 229, 598, 720, 721)
  - **Fresh / Frozen:** Weight receiving, R certificate, FF form, animal-movement license,
    expiration / shelf-life rules + OCR (REV-131, 578, 814, 851, 870, 871, 725)
  - **Auto & consolidated:** Auto receiving, H2H CPF, Consolidated BOL processing
    (REV-602, 900, 890, 892, 894)
  - **Supplier-to-store flow** (REV-188, 652, 656)
  - **Reporting & ops:** Reports, Biz Metrics, dashboard & endpoint monitoring
    (REV-29, 139, 821)
  - **Platform:** New app, Android / Newland device, Email notifications (REV-183, 809, 34)
- **Status:** `active` — v1.0 is in production (Epics "Prod issue from v1.0" and
  "E-Receiving New App" are Done) with weekly enhancement releases ongoing.

## Ownership
- **QA lead:** Kunyapat Tumrongpuvarat (Gift)
- **QA owner (key person for E-Receiving):** Kanchala Kumthim (Miw)
- **Owning QA team:** «to confirm»
- **Reviewers (for changes to this folder):** «to confirm — see /CODEOWNERS»

## What lives here
| Folder | Contents |
|---|---|
| `knowledge/` | Project-specific domain facts: business rules, glossary, defect patterns. |
| `context/`   | Where to fetch requirements (Jira `REV`, Confluence space `HS`) — see `sources.md`. |
| `artifacts/` | Outputs agents produce for this project (reviews, test conditions, test cases). |

## Key systems & integrations (from Jira/BRD — confirm before relying on)
- Integration chain: **E-Receiving App (new stack) → RMS → SIM**
- Systems: **RMS** · **SIM** · **WMOS** · **MSP** · **Kafka** · **H2H/CPF**  _(Mendix is no longer in scope of E-Receiving)_
- Receiving quantity grouped by **Distro No.** across the integration chain
- Related surfaces (visual, not machine-readable): **Miro** (journey), **Figma** (UI)

## How agents use this project
Tell the agent which project to use (e.g. *"review REV-123 for e-receive"*); it loads
`shared/` + this folder and resolves requirement sources from `context/sources.md`.
See `/README.md` for the two usage models.
