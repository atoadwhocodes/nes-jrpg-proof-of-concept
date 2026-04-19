# Assets

This file documents all graphical and audio assets used in the project,
their licensing status, and where they live in the repository.

---

## Tile / CHR data

| Asset | Format | Location | License / Source | Notes |
|---|---|---|---|---|
| Player sprite | 8×16 px (2 tiles) | `assets/chr/player.chr` | Original / placeholder | Single walking frame; expand later |
| Enemy sprite | 16×16 px (4 tiles) | `assets/chr/enemy.chr` | Original / placeholder | Generic slime stand-in |
| Field tileset | 8×8 px × 64 tiles | `assets/chr/field.chr` | Original / placeholder | Grass, dirt, wall, door tiles |
| Battle background | 8×8 px × 64 tiles | `assets/chr/battle_bg.chr` | Original / placeholder | Cave/dungeon stand-in |
| Font / UI tiles | 8×8 px × 64 tiles | `assets/chr/font.chr` | Original / placeholder | ASCII subset A–Z 0–9 symbols |

> **Note:** Files listed above do not yet exist. They will be created as binary
> placeholders (all-zero CHR data) in Milestone 2. Replace them with real art
> at any time without changing the rest of the build.

---

## Audio

No audio assets are in scope for the vertical slice.
Add an entry here when / if audio is introduced.

---

## Licensing rules

- All assets in this repository must be either **original work** or licensed under
  a **permissive / open licence** (CC0, CC-BY 4.0, MIT, or equivalent).
- Do not commit assets from commercial tilesets, ROM rips, or any source that
  requires a paid licence unless explicit written permission has been obtained.
- If an asset is sourced from a third party, add a row to the table above with
  the exact licence name and URL.

---

## Directory layout

```
assets/
  chr/        — raw CHR binary files (.chr)
  palettes/   — palette definition text files (.pal)
src/
  field/      — field / overworld logic
  battle/     — battle logic
  render/     — PPU / rendering helpers
  state/      — game state machine
  lib/        — shared subroutines (math, RNG, controller)
  main.asm    — reset vector, NMI, IRQ, boot sequence
  header.asm  — iNES / NES 2.0 header
Makefile
```
