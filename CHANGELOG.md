# Changelog

All notable changes to this project will be documented in this file.

## [0.1.0.5] - 2026-04-10

### Fixed
- Tiebreaker now only affects rankings after the tournament is complete, not mid-tournament where the leader's incomplete total strokes are incomparable to 4-round predictions
- Entries with equal points correctly share the same rank during the tournament instead of being falsely differentiated
- Equidistant tiebreaker predictions (e.g., 268 and 272 when winner shoots 270) now correctly share ranks and split payouts

### Added
- "T" prefix on tied ranks (e.g., T3, T12) across leaderboard, payouts, detail cards, and projections tabs

## [0.1.0.4] - 2026-04-10

### Added
- GoatCounter event tracking for tab switches, participant expansions, favorites, search queries, stats sorting, rule section opens, and payouts clicks
- Analytics helper with debounced search tracking (fires after 1s pause, 3+ characters)

## [0.1.0.3] - 2026-04-10

### Added
- GoatCounter analytics for anonymous, cookie-free page view tracking

## [0.1.0.2] - 2026-04-10

### Changed
- Worst score penalty for cut players now tracks live during in-progress rounds instead of waiting for the first player to finish all 18 holes
- Penalty only applies when the worst score is at or above par (72+), preventing cut players from receiving positive points during early-round under-par play

## [0.1.0.1] - 2026-04-10

### Fixed
- Swing-o-Meter displayed inverted score-to-par values (e.g., showing +3 when golfer was -3 under par)
- Even par now shows "E" instead of "+0" in Swing-o-Meter

## [0.1.0.0] - 2026-04-10

### Added
- Pool Rules tab with expandable card-based reference for scoring, bonus points, withdrawals, and other rules
- Inline accordion expansion on Leaderboard rows, replacing the old modal and Find Me tab
- Multi-expand support so users can compare multiple entries side by side
- Chevron indicator and gold ring border on expanded rows
- Escape key collapses all expanded entries
- Cross-tab navigation from Payouts "In the Money" list to Leaderboard expansion

### Removed
- Find Me tab (functionality merged into Leaderboard search + inline expansion)
- Detail modal overlay (replaced by inline expansion)

### Changed
- Tab bar reduced from 6 tabs to 5 for cleaner navigation on mobile
