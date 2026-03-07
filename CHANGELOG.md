# PRESS — Changelog

All notable changes to pressgame.live are documented here.

---

## v2.2 — 2026-03-07

### Changed
- **Timer rebalanced** — Flop 45s / Turn 50s / River 60s. Cognitive load grows with each stage: Flop is fast pattern matching, River is full re-evaluation with maximum combinations. Timer now reflects that.
- **No auto-focus on mobile** — input no longer steals focus on round start for mobile devices. Keyboard stays closed until player taps, keeping tiles visible above the fold. Desktop behavior unchanged.

---

## v2.1 — 2026-03-06

### Changed
- **Lock now ends your round immediately** — no more limbo state after locking. Once you lock, the round resolves and the AI plays out. Lock + Press is no longer a valid path.
- **Penalty simplified** — the −3 press penalty now only applies when you Press and your final word is no longer than the word you had saved before pressing. Never applies to Lock.
- **"Word saved" reassurance** — when you Press with a valid word typed, a subtle confirmation appears: e.g. "✓ CODER saved — hunting for better." Your safety net is now visible.

### Added
- **What's New banner** on home screen — lightweight, dismissable, shows returning testers what changed. Remembers dismissal via localStorage.

### Updated
- How to Play slide 2 updated to reflect new Lock behavior and Press safety net mechanic

---

## v2.0 — 2026-03-06

### Added
- **Early lock bonus** — Lock at Flop earns +2pts; Lock at Turn earns +1pt; River submit earns no bonus. The Lock button now displays the active bonus (+2 / +1) so players can see exactly what they're giving up before pressing. Designed to make locking a genuinely tempting choice rather than a trap.
- **Three AI tiers with distinct philosophies:**
  - **Casual** — locks early and chases the bonus aggressively. Locks at Flop whenever any valid word is available. Never presses unless there's no word yet.
  - **Strategic** (default) — calculates expected value. Weighs the lock bonus against potential word improvement. The baseline opponent.
  - **Mastermind** — ignores the bonus entirely. Only locks/submits when holding a 7-letter word or maximum-scoring word. Always presses for more if a better word is theoretically reachable.
- **Result screen upgrade — full transparency:**
  - All 5 community tiles are now shown on the result screen regardless of when the player locked
  - Stage indicator badge on each result card: e.g. "locked at Flop", "locked at Turn", "submitted at River"
  - AI badge shows which stage Strategic locked or submitted at
- **Best possible word** now calculated from all 8 tiles (3 private + all 5 community), not just tiles visible at submission

### Changed
- How to Play modal updated: Lock/Press slide now mentions early lock bonuses; Scoring slide lists +2 Flop / +1 Turn bonus rows; max possible score updated to 23pts

---

## v1.6 — 2026-03-05

### Fixed
- **Stage track redesigned** — FLOP / TURN / RIVER labels are now fixed anchors, always visible, with pips running between them. Active stage highlights in green, others dim. Eliminates the stale/duplicate label bug entirely
- **Locked state hint added** — after locking without pressing, a subtle prompt now appears: "Type a better word to re-lock, or Press to the river." Eliminates the dead-end feeling of a stopped timer with no guidance

---

## v1.5 — 2026-03-05

### Fixed
- **Timer stops on Lock** — previously the timer restarted after locking, leaving the player in a pointless countdown with nothing to do. Timer now stops on Lock and only restarts if the player chooses to Press
- **Auto-lock respects existing locked word** — previously if the timer expired after a Lock with an empty input field, the player scored zero. Now if a locked word exists and the input is empty at expiry, the locked word is used as the final score

---

## v1.4 — 2026-03-05

### Fixed
- **Stage labels reset correctly between rounds** — TURN and RIVER labels were persisting from the previous round, causing the stage track to show incorrect labels (e.g. RIVER / TURN / RIVER) at the start of a new round. All labels now reset to FLOP / TURN / RIVER on every renderStage call

---

## v1.3 — 2026-03-05

### Fixed
- **Lock re-enables after first use** when a new valid word is typed — previously Lock stayed permanently disabled after locking, preventing players from upgrading to a better word at a later stage. Lock now re-enables dynamically whenever a valid word is in the input field, and disables again if the input is cleared

---

## v1.2 — 2026-03-05

### Fixed
- **Lock no longer immediately resolves the round** — previously hitting Lock ended the round instantly, making Press after Lock impossible. Lock now banks your word and keeps you in the game. Press remains active. Round only resolves at Submit, auto-lock, or Lock at the river
- **Lock button disables after use** — once you've locked a word you can't re-lock, only press forward or wait for the river
- **Penalty warning now stays visible** for the full remainder of the round after pressing with a locked word

---

## v1.1 — 2026-03-05

### Fixed
- **Best word reveal** now only shows words formable from tiles visible at the time of submission — previously could suggest words using hidden community letters
- **Vowel floor tightened** — now guarantees at least 1 vowel in the first 6 tiles (3 private + 3 flop), eliminating vowel-less opening deals

---

## v1.0 — 2026-03-05

### Launched
- Initial release at pressgame.live
- Full 24,956 word dictionary (SCOWL source, filtered to 5–7 letters, profanity removed)
- Core game loop — Flop / Turn / River with Lock or Press decision at each stage
- Press penalty — lose 3pts from locked score if you press and fail to improve word length
- Auto-lock on timer expiry — valid typed word locks, empty input scores zero
- Strategic AI opponent with thinking state and simultaneous reveal
- Scoring model — 5/9/15pts by length, +2 bonuses for all privates / rare letter / all unique
- Best possible word reveal after every round (the RAISIN moment)
- How to Play — 3-slide paginated modal with visual tile examples
- Home screen with tagline and decorative tiles
- Feedback form via Formspree
- Home button on result screen
- Community tiles on top (the table), hand on bottom (closest to player)
