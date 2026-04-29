# Postmortem — schema_validation_error

**Cluster:** `ext_bce974a1`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-28 18:28:23 UTC |
| Recovery confirmed | 2026-03-15 17:09:06 UTC |
| Time to recovery | **1291243s** |

---

## What Broke

**Tool:** `edit_file`  
**Input:** `fix(sequential-thinking): Use z.coerce for inputSchema to handle string-typed parameters from LLM clients ## Problem  Mu…`  

**Error:**
```
(same as before)
```

---

## What Worked

**Tool:** `edit_file`  
**Input:** `proposed (but not merged) in #2812.`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1291243s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-28 18:28:23 UTC |
| Last seen | 2026-03-15 17:09:06 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: schema_validation_error in edit_file is recoverable via edit_file in 1291243s — no human required._
