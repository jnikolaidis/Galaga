# CHANGELOG — Galaga

_Append-only log of verified milestones: date, what, commit ref, verification.
Never edit or delete entries._

## 2026-09-19 — Agent contract + durable memory installed

- Replaced the previous CLAUDE.md contract (full content preserved: gotchas →
  MEMORY.md, stack/commands → AGENTS.md; CLAUDE.md is now a thin pointer to
  AGENTS.md) and installed the customized SuperExecutor contract plus the
  canonical durable-memory documents. The pre-existing uncommitted game
  changes were left untouched. Performed by John's ZCode agent at his
  direction; documentation-only change, no verification round. Not yet
  committed — awaiting John's review.

## 2026-09-19 — Contract handoff reconciled against git state

- Corrects the entry above: its "Not yet committed — awaiting John's review"
  line went stale. The contract was committed and pushed as `cf905aa`, and
  STATUS.md's handoff and branch claims were reconciled against real git state.
  Also corrected the Current state/Board/Open-decisions sections: the
  audit/remediation change set is committed as `73ea550` and the working tree
  is clean, so this entry's "left untouched" line records that session's own
  action, superseded by the commit that followed it. Documentation-truth fix
  only; no product code changed. Verified with `git log`, `git status`, and a
  workspace-wide grep for the pre-rename path.
