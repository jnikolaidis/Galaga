# Galaga

A single-file Galaga arcade clone built with HTML5 Canvas and vanilla JavaScript. Each stage sends 40 enemies swooping in along Bezier-curve entry paths to form a breathing formation, from which they peel off in dive attacks. Boss Galaga can catch your fighter in a tractor beam — shoot the boss to free it and catch the fighter back to fly as a dual fighter. Includes challenge bonus stages, procedural Web Audio sound, touch controls, and a persistent high score. No build system, no dependencies.

## How to Run

Open `index.html` in any modern browser — double-click it or serve the directory statically. There is nothing to install.

## Controls

| Key | Action |
| --- | --- |
| `←` `→` or `A` `D` | Move |
| `Space` | Fire (hold for continuous fire; `↑` also fires) |
| `P` | Pause / resume |
| `Q` / `X` / `Esc` | Quit |
| `Space` or `Enter` | Start game |

Sound starts off — click the **SOUND** button to toggle it on.

**Pointer:** click the canvas to start (or restart). **Touch:** drag to move, auto-fire while touching, tap to start.

## Gameplay

- **Enemies:** 40 per stage — 4 boss Galaga, 16 butterflies, 20 bees. They enter along Bezier curves, settle into a formation that breathes in and out, and launch dive attacks.
- **Tractor beam:** a diving boss can deploy a tractor beam. If it catches your fighter, the boss carries it back to the formation. Shoot that boss on its next dive to release the fighter, then catch it as it drifts down — you now fly two fighters side by side. Rescuing a captured fighter scores 1,000 points.
- **Challenge stages:** every 4th stage (3, 7, 11, ...) is a bonus stage. Enemies fly through in patterns without firing; each hit is worth 100 points, and destroying all 40 awards a 10,000-point perfect bonus.
- **Scoring:**

  | Enemy | In formation | Diving |
  | --- | --- | --- |
  | Bee | 50 | 100 |
  | Butterfly | 80 | 160 |
  | Boss Galaga | 150 | 400 alone, 800 with 1 escort, 1600 with 2 escorts |

  An escort counts toward the boss bonus as long as it is still alive, even if it has already finished its own dive. Enemies still flying their entry path have not dived yet, so they pay the "in formation" rate.

- **Extra lives:** awarded at 20,000 points, then every 70,000.

## Technical Notes

- The entire game lives in a single `index.html` (~3,000 lines of inline JavaScript). No build step, no frameworks, no external assets.
- Canvas 2D rendering at a native resolution of 224×288, drawn at 3x (672×864). The canvas scales to fit the window (capped at 2x) while preserving the aspect ratio.
- Sprites are drawn programmatically from pixel-art arrays — no image files.
- All sound effects are synthesized procedurally with the Web Audio API — no audio files.
- The high score persists in `localStorage` (key `galaga_hs`).
- `galaga.html` is a standalone copy of the game for distribution. It is byte-identical to `index.html` — after editing `index.html`, re-sync it (`cp index.html galaga.html`). CI (`.github/workflows/checks.yml`) fails the build if the two copies drift apart.

## License

MIT — see [LICENSE](LICENSE).
