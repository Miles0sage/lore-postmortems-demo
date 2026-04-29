# Postmortem — schema_validation_error

**Cluster:** `ext_1294daab`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-12-23 07:34:03 UTC |
| Recovery confirmed | 2025-12-28 19:51:53 UTC |
| Time to recovery | **476270s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `linear_update_issue: status parameter expects stateId UUID but schema implies status name ## Bug Description  The `linea…`  

**Error:**
```
Argument Validation Error - stateId must be a UUID
```

---

## What Worked

**Tool:** `read_file`  
**Input:** `Option A (Better UX): Look up workflow states and resolve name → UUID:`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 476270s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-12-23 07:34:03 UTC |
| Last seen | 2025-12-28 19:51:53 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: schema_validation_error in read_file is recoverable via read_file in 476270s — no human required._
