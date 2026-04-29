# Data Gap — failure with no recovery captured

**Session:** `36d06f83-6995-49a2-9677-aa100bdd5767`  
**Short ID:** `36d06f83`  
**Source:** `/root/claude-brain/dpo-pairs/2026-04-28.skipped.jsonl`

---

## What This Means

A tool failure was logged in this session but no successful recovery was observed within the harvest window. This is significant: it means either the agent session terminated before finding a fix, or the fix occurred in a different session that was not captured.

This class of failure is the most dangerous — the agent stalled with no auto-recovery. Lore's job is to detect and flag these in real-time.

---

## Failure Details

**Tool that failed:** `unknown`  
**Reason skipped:** `no_chosen_in_window`  

**Error preview:**
```
(no preview)
```

---

## Why This Is Interesting

- Sessions that die before recovery represent **unresolved stalls** — the class of failure Lore is designed to prevent.
- Each data-gap session is a candidate for proactive intervention: Lore could detect the failure signature and inject a recovery suggestion before the session terminates.
- Accumulating these gaps builds the 'failure fingerprint' database that drives Darwin evolution.

---

_Lesson Lore would route around: sessions that terminate mid-failure are the highest-value training signal — they show exactly where autonomous recovery is missing._
