# PROJECT — Galaga

_Stable product baseline: what this is, phases, decisions. Update only when
direction changes; live state belongs in STATUS.md._

## What this is

A single-file Galaga arcade clone: Bezier flight paths, breathing formation,
tractor-beam capture / dual fighter, challenge stages, procedural Web Audio,
localStorage high score. No build system, no dependencies. A live copy ships
on jnikolaidis.com from the site repo.

## Stack

- HTML5 Canvas, vanilla ES6 JavaScript, Web Audio API, localStorage — all
  inline in one file

## Phases

- Build (complete) → audit/remediation (see `tasks/todo.md`; uncommitted
  change set in flight as of 2026-09-19) → maintenance.

## Decisions

- 2026-09-19 — This repo runs under the SuperExecutor agent contract
  (AGENTS.md); durable memory lives in the five canonical documents.
- Byte-identical `galaga.html` shareable copy, enforced by CI.
- The live public copy is deployed from the `jnikolaidis.com` repo, never
  from here.
