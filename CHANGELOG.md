# PRESS — Changelog

All notable changes to pressgame.live are documented here.

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
