# Postmortem — resource_not_found

**Cluster:** `ext_1808ac3c`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-05-15 12:11:59 UTC |
| Recovery confirmed | 2025-08-01 17:12:32 UTC |
| Time to recovery | **6757233s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `IST zone not supported yet!   File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/zoneinfo/_common.p…`  

**Error:**
```
'No time zone found with key IST'
```

---

## What Worked

**Tool:** `unknown`  
**Input:** ``  

**Result (truncated):**
```

```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 6757233s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-05-15 12:11:59 UTC |
| Last seen | 2025-08-01 17:12:32 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via unknown in 6757233s — no human required._
