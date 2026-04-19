Read README.md, MILESTONES.md, AGENT_RULES.md, and ASSETS.md before making changes.

This repository is an NES party-based turn JRPG proof of concept in 6502 assembly.

Primary goal:
Build only the first playable vertical slice:
field -> encounter -> battle -> result -> return to field

Technical constraints:
- NES
- UNROM-512 + CHR RAM
- ca65/ld65
- top-down exploration
- front-view battle
- bottom menu/status windows

Scope constraints:
- Do not add inventory pages
- Do not add equipment menus
- Do not add shops
- Do not add save systems
- Do not add long story scenes
- Do not add deep magic systems
- Do not add multiple enemy groups unless explicitly asked
- Do not expand scope to be helpful

Engineering rules:
- Keep field, battle, render, and state logic separated
- Every file should have one clear responsibility
- Prefer simple hardcoded placeholders when they speed up the proof of concept
- Stop after the requested milestone
- Report files changed, blockers, and exact next action
