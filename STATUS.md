# STATUS — Galaga

_One current-state view. Update at every milestone, blocker or next-action
change (see AGENTS.md → Milestone banking)._

## Current state

- **Branch:** `main`, in sync with `origin/main` — **but the working tree
  carries a large UNCOMMITTED change set** (as of 2026-09-19): `index.html`
  and `galaga.html` each modified (~462 insertions / 434 deletions; the two
  copies are byte-identical to each other), modified `.gitignore`, `README.md`,
  plus untracked `.github/` (the CI workflow) and `LICENSE`. `CLAUDE.md` was
  also modified-uncommitted; it has since been replaced by the thin-pointer
  pattern (its gotchas live in MEMORY.md now).
- **Phase:** audit/remediation in flight — see `tasks/todo.md`.
- Any session starting here must first understand this uncommitted work before
  touching anything (boot sequence step 5).

## Board

- [ ] Review, verify, and commit (or explicitly discard) the uncommitted
  game/CI/license change set — John's call on timing.
- [ ] Close remaining items in `tasks/todo.md`, if any.

## Open decisions

- Whether the uncommitted change set ships as-is or gets another pass —
  waiting on John.

## Session handoff

### 2026-09-19 — SuperExecutor contract installed

- **Done:** installed the agent contract (AGENTS.md, customized from
  `JNProjects/AGENTS.md.template`) and the durable-memory docs
  (STATUS/MEMORY/CHANGELOG/PROJECT/MEMORY_ARCHIVE). The previous CLAUDE.md
  contract was replaced by a thin pointer; its full content was preserved —
  gotchas → MEMORY.md, stack/commands → AGENTS.md. **The uncommitted game
  changes were NOT touched.**
- **In flight:** the pre-existing uncommitted change set described above
  (not started by the contract session).
- **Exact next steps:** boot per AGENTS.md; reconcile the uncommitted work
  (diff review → verify → commit or discard) with John.
- **Waiting on John:** fate of the uncommitted change set; review and commit
  of the new contract files.
