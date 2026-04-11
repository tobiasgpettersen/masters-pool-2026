# TODOS

## Consolidate ownership computation into single global index
**Why:** Ownership data ("who picked this golfer") is computed in 3 places: `renderStats` (ownerEntries, lines 1008-1017), `openEntryModal` (modalOwnerList, lines 1460-1472), and the new `golferOwnersIndex` (built after calculateAllScores). Each recomputes from ENTRIES independently.

**What to do:** Make `golferOwnersIndex` the single source of truth. Replace `ownerEntries` in renderStats and `modalOwnerList` in openEntryModal to read from the global index instead of recomputing. The index already has rank, points, and entryIdx per owner.

**Blocked by:** Ship the golfer ownership modal first (current branch). Then consolidate.

**Added:** 2026-04-11 by /plan-eng-review (Codex identified the DRY violation)
