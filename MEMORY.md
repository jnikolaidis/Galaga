# MEMORY — Galaga

_Active traps and gotchas that change agent behavior. When a trap is resolved,
move its entry to MEMORY_ARCHIVE.md — nothing is silently deleted.
Carried over from the previous CLAUDE.md contract (2026-09-19)._

## Active traps

- Entire game is one `index.html` file with ~3,000 lines of inline JS.
- `galaga.html` is a standalone copy of the game — after editing
  `index.html`, re-sync it (`cp index.html galaga.html`) or the copies drift.
  CI (`.github/workflows/checks.yml`) enforces byte-identity plus a parse
  check of the inline script.
- Losing window focus (blur or tab hidden) auto-pauses an active run; audio is
  suspended while hidden.
- Sound effects synthesized procedurally via Web Audio (no audio files);
  sprites drawn programmatically as pixel art arrays (no image files).
- 40 enemies with Bezier curve entry/dive paths and formation breathing; boss
  tractor-beam capture and dual-fighter rescue mechanics; challenge stages
  every 4th stage (3, 7, 11, …).
- Canvas scales dynamically to the window while maintaining aspect ratio;
  native resolution 224×288 rendered at 3× scale (672×864).
- Touch controls for mobile (drag to move, auto-fire).
- No local test suite — verification is CI's parse/identity checks plus
  browser smoke testing.
