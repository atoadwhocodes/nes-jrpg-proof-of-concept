# Milestones

This is the exact build order for the NES JRPG proof-of-concept vertical slice.
Complete each milestone before starting the next.

---

## Milestone 1 — Black screen boots

**Goal:** ROM compiles and runs; NES initialises without crashing.

- [ ] ca65/ld65 build system wired up (Makefile)
- [ ] UNROM-512 mapper header in place
- [ ] Reset vector, NMI stub, and IRQ stub defined
- [ ] PPU initialisation routine (disable rendering, clear VRAM)
- [ ] ROM boots to a stable black screen in Mesen or FCEUX

**Definition of done:** ROM loads, reaches the infinite loop after init, does not reset or crash.

---

## Milestone 2 — Field screen with player tile

**Goal:** A single room is visible; the player tile appears on screen.

- [ ] CHR RAM tile loading from PRG data
- [ ] Static nametable for a placeholder room (16×15 tiles)
- [ ] Player sprite drawn at a fixed starting position
- [ ] Background palette and sprite palette loaded
- [ ] Screen is enabled (PPUMASK write)

**Definition of done:** Player tile is visible on a plain background room.

---

## Milestone 3 — Player movement

**Goal:** D-pad moves the player one tile at a time.

- [ ] Controller read routine (poll twice for reliability)
- [ ] Player X/Y tile position stored in RAM
- [ ] Movement updates sprite position each frame via NMI
- [ ] Collision stub (all tiles passable for now)
- [ ] Player cannot walk off-screen

**Definition of done:** Player tile moves with the D-pad and stays inside the screen boundary.

---

## Milestone 4 — Random encounter trigger

**Goal:** Walking on certain tiles has a chance to start a battle.

- [ ] Step counter incremented on each tile move
- [ ] Random number generator (linear feedback shift register or similar)
- [ ] Encounter check after each step (configurable rate constant)
- [ ] Game state flag (`STATE_FIELD` / `STATE_BATTLE`) set when encounter fires
- [ ] Screen fades to black when encounter triggers (or hard-cut is acceptable)

**Definition of done:** After a random number of steps the game state switches to battle.

---

## Milestone 5 — Front-view battle screen

**Goal:** A placeholder battle screen appears with enemy sprite and status windows.

- [ ] Nametable for battle background loaded
- [ ] Enemy sprite drawn at fixed position
- [ ] Bottom status window: party names and HP values (hardcoded placeholders)
- [ ] Bottom menu window: Attack / Magic / Item / Run (text tiles)
- [ ] Cursor rendered on first menu option

**Definition of done:** Battle screen is displayed with enemy, status bar, and menu visible.

---

## Milestone 6 — Battle menu input and turn loop

**Goal:** The player can select Attack; a simple turn resolves; battle ends.

- [ ] Cursor moves between menu options with D-pad Up/Down
- [ ] Pressing A on Attack triggers player attack phase
- [ ] Placeholder damage calculation (fixed value or simple formula)
- [ ] Enemy HP reduced; value updated in status window
- [ ] When enemy HP ≤ 0, game state switches to `STATE_RESULT`

**Definition of done:** Player selects Attack, enemy HP decreases, battle ends when HP hits zero.

---

## Milestone 7 — Battle result screen

**Goal:** A "Victory" result screen appears after battle.

- [ ] Result screen nametable (or text overlay) loaded
- [ ] "VICTORY" text (or equivalent tile art) displayed
- [ ] EXP / gold placeholder values shown (hardcoded)
- [ ] Press A to continue prompt
- [ ] After A press, game state switches to `STATE_FIELD`

**Definition of done:** Result screen appears, player presses A, and the field returns.

---

## Milestone 8 — Return to field after battle

**Goal:** The field resumes at the player's saved position after a battle.

- [ ] Player tile position preserved across state transitions
- [ ] Field nametable reloaded cleanly on return
- [ ] Encounter step counter reset after battle
- [ ] No visual glitches on return to field
- [ ] Full loop verified: field → encounter → battle → result → field

**Definition of done:** The complete vertical slice loop runs end-to-end without crashes.

---

## Milestone 9 — Interior room transition (stretch goal)

**Goal:** One doorway moves the player to a second room.

- [ ] Second room nametable defined
- [ ] Door trigger tile(s) in first room
- [ ] Room-load routine swaps nametable data
- [ ] Player placed at correct entry point in new room
- [ ] Back-door returns player to original room entry point

**Definition of done:** Player walks through a door, second room loads, player can walk back.

---

## Out of scope (do not add)

- Inventory pages
- Equipment menus
- Shops
- Save / load system
- Long story scenes or cutscenes
- Deep magic systems
- Multiple enemy groups (unless explicitly requested)
- Sound / music (unless explicitly requested)
