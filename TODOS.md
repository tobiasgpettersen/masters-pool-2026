# TODOS

## Consolidate ownership computation into single global index
**Why:** Ownership data ("who picked this golfer") is computed in 3 places: `renderStats` (ownerEntries, lines 1008-1017), `openEntryModal` (modalOwnerList, lines 1460-1472), and the new `golferOwnersIndex` (built after calculateAllScores). Each recomputes from ENTRIES independently.

**What to do:** Make `golferOwnersIndex` the single source of truth. Replace `ownerEntries` in renderStats and `modalOwnerList` in openEntryModal to read from the global index instead of recomputing. The index already has rank, points, and entryIdx per owner.

**Blocked by:** Ship the golfer ownership modal first (current branch). Then consolidate.

**Added:** 2026-04-11 by /plan-eng-review (Codex identified the DRY violation)

## Verify ESPN eventStatus values during a real playoff
**Why:** The playoff bonus fix gates `tournamentComplete` on `eventStatus` matching "Final". The entire fix assumes ESPN uses "In Progress" (or similar) during a playoff and "Final" after. This assumption is unverified against real ESPN data.

**What to do:** During the next golf tournament with a playoff (or by querying historical ESPN scoreboard API data, e.g., 2017 Masters / Sergio Garcia playoff), capture the actual `event.status.type.description` values at each stage: R4 complete, playoff in progress, playoff resolved. Log the values to confirm the assumption.

**Blocked by:** Nothing. Can verify during any PGA playoff, or by searching for archived ESPN API responses.

**Added:** 2026-04-12 by /plan-eng-review (outside voice flagged unverified assumption)
