# Contributing

How to extend the framework without stepping on other teams.

## Golden rules

1. **Edit only your own project folder** (`projects/<your-project>/`) for day-to-day work.
2. Changes to `shared/` or `agents/` are **framework-wide** — they need review by the
   maintainers listed in [CODEOWNERS](CODEOWNERS), because every team depends on them.
3. Keep the **path convention**: reference files relative to the framework root
   (e.g. `shared/config/guardrails.md`). Use `<PROJECT>` as the active-project placeholder.
4. Put knowledge at the right layer (see the table in [README.md](README.md)). When in
   doubt: shared if it's cross-team, project if it's system-specific.

---

## Add a new project (onboard a team) — ~5 minutes

1. Copy `projects/_template/` → `projects/<your-slug>/` (lowercase, kebab-case).
2. Fill in the `README.md` (owner, contact, scope).
3. Fill in `knowledge/business-rules.md`, `knowledge/glossary.md`,
   `knowledge/defect-patterns.md` with what's specific to your system.
4. Fill in `context/sources.md` (Jira keys, Confluence space, repo).
5. Add your slug to the **Projects** table in `README.md` and an entry in `CODEOWNERS`.
6. Do **not** duplicate rules already in `shared/knowledge/` — reference them instead.

Nothing under `shared/` or `agents/` changes — that's the point.

---

## Add a new agent (new capability)

1. Copy the shape of `agents/qa-requirement-agent/` → `agents/<new-agent>/`
   (`agent.md` + `config/` + `skills/` + `templates/`). The scaffold in
   `agents/qa-test-design-agent/` shows the minimum.
2. The agent's `agent.md` is its entry point. It must:
   - resolve the **active project** (§0.1 pattern) before using domain knowledge;
   - inherit `shared/config/guardrails.md` and `shared/config/output-schema.md`;
   - reference shared knowledge/tools rather than copying them.
3. Keep agent-specific rubrics/templates inside the agent folder; keep anything reusable
   in `shared/`.
4. Register the agent in the **Agents** table in `README.md` and in `CODEOWNERS`.

---

## Review & ownership

- `CODEOWNERS` maps folders → reviewers. A change to a folder needs its owner's approval.
- `shared/` and `agents/` = framework maintainers. `projects/<x>/` = that project's team.
- This keeps many teams in one repo with minimal merge conflicts: teams touch their own
  project folders; shared changes go through a deliberate review.
