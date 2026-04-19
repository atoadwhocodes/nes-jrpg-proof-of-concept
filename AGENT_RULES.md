# Agent Rules

Rules for any AI agent (GitHub Copilot or otherwise) working on this repository.
Read this file before touching any code.

---

## Scope rules — what NOT to add

- Do not add inventory pages
- Do not add equipment menus
- Do not add shops or vendors
- Do not add a save / load system
- Do not add long story scenes or cutscenes
- Do not add a deep or branching magic system
- Do not add multiple enemy groups unless explicitly asked
- Do not expand scope "to be helpful" — build only what the current milestone requires
- Do not add sound or music unless explicitly asked

---

## Engineering rules

- Keep field logic, battle logic, render logic, and game-state logic in **separate files**
- Every file should have **one clear responsibility**
- Use simple hardcoded placeholder values when they speed up the proof of concept
- Do not refactor working code that is not part of the current milestone
- Do not rename symbols or reorganise file structure without an explicit instruction to do so

---

## Build rules

- Target: NES (NTSC)
- Mapper: UNROM-512 (mapper 30) with CHR RAM
- Assembler / linker: ca65 and ld65
- Do not introduce a different assembler or build tool without explicit approval
- The ROM must pass a basic boot test in Mesen or FCEUX before a milestone is marked done

---

## Output rules

After completing any milestone, report:

1. **Summary** — what was built
2. **Files created / changed** — list every file and why it changed
3. **Blockers** — anything that prevents the next milestone
4. **Exact next action** — the single most useful next step

---

## Stop conditions

- Stop after the requested milestone is complete
- If a task is ambiguous, stop and ask rather than guessing and over-building
- If a required asset is missing, stop and report what is needed
