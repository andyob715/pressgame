# PRESS — Changelog

All notable changes to pressgame.live are documented here.

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
