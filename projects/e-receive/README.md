# Project: E-Receive

> Seeded from `projects/_template/`. Fill in every `<...>` placeholder below and in the
> files under `knowledge/` and `context/` with the real E-Receive details.

---

## Overview
- **Slug:** `e-receive` (this is the value that goes in the `project` output field)
- **System / scope:** <what this system does, one paragraph>
- **Status:** <active / onboarding>

## Ownership
- **Owning QA team:** <team name>
- **Point of contact:** <name / email / Slack channel>
- **Reviewers (for changes to this folder):** <who approves PRs here — see /CODEOWNERS>

## What lives here
| Folder | Contents |
|---|---|
| `knowledge/` | Project-specific domain facts: business rules, glossary, defect patterns. |
| `context/` | Where to fetch requirements (Jira project keys, Confluence spaces) — see `sources.md`. |
| `artifacts/` | Outputs produced by agents for this project (reviews, test conditions, test cases). |

## How agents use this project
Any agent in the framework can work on this project. Tell the agent which project to
use (e.g. *"review PROJ-123 for `<slug>`"*); it then loads `shared/` + this folder.
See `/README.md` for the two usage models (per-team Claude Project vs. one combined project).
