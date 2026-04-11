# Changelog

All notable changes to this project will be documented in this file.

## [0.1.1.2] - 2026-04-11

### Fixed
- Active players sharing a score with cut/WD players no longer show inflated positions from ESPN (positions recomputed from active-player pool only)
- Position "T" prefix now only appears for actual ties among active players (was hardcoded on every position)
- WD/DQ players no longer block cut detection by failing the all-R2-complete check

## [0.1.1.1] - 2026-04-11

### Fixed
- Players who missed the cut now detected independently from ESPN data using 2-round stroke totals (top 50 and ties rule), since ESPN's API delays flagging cut status
- Cut players receive the worst score of the day penalty for rounds they don't play (live-updating as R3/R4 scores come in)
- Position column shows "MC" (Missed Cut) in red for cut players instead of their old position number
- Positions recomputed after cut detection so only active players are ranked (no inflated positions from cut players)
- Player Stats default sort changed to position ascending (leaderboard order) instead of pool points

## [0.1.1.0] - 2026-04-11

### Added
- Participant detail modal on Player Stats page: click any participant name in a golfer's expanded row to see their full team breakdown in a popup overlay
- Relationship lens: connecting golfer is highlighted with golden ring and "LINKED" badge in the modal
- Context chip showing which golfer connects you to the participant, with pick type, points contributed, and ownership percentage
- Prev/next navigation to browse through all owners of the same golfer without closing the modal (wraps around)
- Bidirectional linking: click any golfer name in the modal to jump to that golfer's Player Stats row
- Keyboard navigation: Escape closes modal, Left/Right arrows navigate between owners
- Modal auto-refreshes when live data updates during the tournament
- iOS-compatible scroll lock prevents background scrolling when modal is open
- Accessible modal with role="dialog", aria-modal, and proper close behavior

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
