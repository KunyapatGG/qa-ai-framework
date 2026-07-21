# Tool: Git

Inspect code/diffs to support **traceability** — confirming that a change touches the area a requirement describes, and that acceptance criteria have corresponding implementation.

---

## Purpose
- Read diffs / PRs for the requirement under review.
- Check that changed files map to the traced acceptance criteria.
- Detect scope creep (code changes not covered by any AC) and gaps (ACs with no code).

## Typical commands
| Action | Command |
|---|---|
| Current changes | `git status`, `git diff` |
| Diff vs. base branch | `git diff <base>...<branch>` |
| Files in a PR | `git diff --name-only <base>...<branch>` |
| History of a file | `git log --oneline -- <path>` |
| Who changed a line | `git blame <path>` |

> Note: the primary working directory of this environment is **not** a git repo. Point the agent at the target repository path when using this tool.

## Usage rules
- **Read-only.** This agent never commits, pushes, or modifies source.
- Used mainly by the `traceability` skill.
- Findings feed the traceability matrix (AC → code → test).

## Out of scope
- Code review for correctness/style (this is a *requirement* agent, not a code reviewer).
