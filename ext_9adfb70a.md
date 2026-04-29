# Postmortem — resource_not_found

**Cluster:** `ext_9adfb70a`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-10 16:20:08 UTC |
| Recovery confirmed | 2025-08-01 17:12:23 UTC |
| Time to recovery | **12444735s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Time server fails under EDT timezone **Describe the bug** Running the Time server results in a failure due to local time…`  

**Error:**
```
Traceback (most recent call last):
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 12444735s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-10 16:20:08 UTC |
| Last seen | 2025-08-01 17:12:23 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via unknown in 12444735s — no human required._
