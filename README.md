# QA AI Framework

A shared, multi-agent QA framework for retail. Multiple QA people from multiple teams
use the **same agents** against **their own project knowledge**.

Three layers, kept deliberately separate:

| Layer | Answers | Owned by | Path |
|---|---|---|---|
| **Shared** | Framework rules, tools, universal QA craft | Framework maintainers | `shared/` |
| **Agents** | Reusable *capabilities* (who does the work) | Framework maintainers | `agents/` |
| **Projects** | Domain knowledge per system (E-Receive, Inventory…) | The owning QA team | `projects/` |

> **One agent × one project = one piece of work.** The agent brings the *how*; the
> project brings the *what*. Add a project without touching agents; add an agent without
> touching projects.

---

## Layout

```
qa-ai-framework/
├── README.md            ← you are here
├── CONTRIBUTING.md      ← how to add a project or an agent
├── CODEOWNERS           ← who reviews which folder
│
├── shared/              ← project-agnostic + agent-agnostic
│   ├── config/          guardrails.md, output-schema.md
│   ├── knowledge/       universal QA craft (guideline, techniques, defect-patterns,
│   │                    glossary) + company-wide retail-business-rules.md
│   └── tools/           jira/ confluence/ git/ api/  (MCP-backed integrations)
│
├── agents/              ← reusable capabilities
│   ├── qa-requirement-agent/   agent.md + config/ + skills/ + templates/   (ACTIVE)
│   └── qa-test-design-agent/   scaffold (TODO)
│
├── projects/            ← domain knowledge, one folder per system, team-owned
│   ├── _template/       copy this to onboard a new project
│   ├── e-receive/
│   └── inventory/
│
└── docs/                agent-flow.html
```

## Path convention

Every cross-file reference is written **relative to this framework root**
(e.g. `shared/config/guardrails.md`). `<PROJECT>` is a placeholder for the active
project's folder name under `projects/`.

## Knowledge lives at the right layer

- **Universal QA craft** (applies to every team) → `shared/knowledge/`
- **Company-wide retail rules** (baseline for all projects) → `shared/knowledge/retail-business-rules.md`
- **Project-specific rules/terms/patterns** → `projects/<PROJECT>/knowledge/`

If a QA on another team would also need a rule, it belongs in `shared/`, not a project.

---

## How to use it (two models)

**A. One Claude Project per team** *(recommended when data must stay separated)*
Each team creates its own Claude.ai Project and uploads: `shared/` + the agent(s) they
use + **only their** `projects/<their-project>/`. Knowledge never crosses teams.

**B. One combined Claude Project**
Upload the whole framework. Tell the agent which project to work on
(*"review PROJ-123 for e-receive"*); it loads `shared/` + `projects/e-receive/`.
The agent resolves the active project per `agents/<agent>/agent.md §0.1`.

In both models: **start the session by loading the chosen agent's `agent.md`** — it is
the entry point and orchestrates everything else.

---

## Agents

| Agent | Purpose | Status |
|---|---|---|
| [qa-requirement-agent](agents/qa-requirement-agent/agent.md) | Reviews requirements for clarity/completeness/testability; gives a readiness verdict. | ✅ Active |
| [qa-test-design-agent](agents/qa-test-design-agent/agent.md) | Turns ready requirements + test conditions into executable test cases. | 🚧 Scaffold |

## Projects

| Project | Team | Status |
|---|---|---|
| [e-receive](projects/e-receive/README.md) | _TBD_ | Onboarding |
| [inventory](projects/inventory/README.md) | _TBD_ | Onboarding |

See [CONTRIBUTING.md](CONTRIBUTING.md) to add your own.
