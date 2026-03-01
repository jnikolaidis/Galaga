# Galaga

Single-file Galaga arcade clone with Bezier curve flight paths, tractor beam capture, dual fighter mechanics, challenge stages, and Web Audio sound effects.

## Stack
- HTML5, Vanilla JavaScript (ES6)
- Canvas 2D rendering
- Web Audio API (procedural sound synthesis)
- localStorage (high score)

## Commands
No build system. Open `index.html` in a browser.

## Gotchas
- Entire game is one `index.html` file with ~3500+ lines of inline JS
- Sound effects synthesized procedurally via Web Audio (no audio files)
- Sprites drawn programmatically as pixel art arrays (no image files)
- 40 enemies with Bezier curve entry/dive paths and formation breathing
- Boss Galaga tractor beam capture and dual fighter rescue mechanics
- Challenge stages every 4th stage (3, 7, 11, ...)
- Canvas scales dynamically to window while maintaining aspect ratio
- Touch controls for mobile (drag to move, auto-fire)
- Native resolution 224x288 rendered at 3x scale (672x864)
