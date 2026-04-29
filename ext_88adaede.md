# Postmortem — permission_error

**Cluster:** `ext_88adaede`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-08-11 19:29:24 UTC |
| Recovery confirmed | 2026-02-11 14:57:55 UTC |
| Time to recovery | **15881311s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `filesystem: Incorrect Path resolution causes "Error: Access denied - path outside allowed directories" **Describe the bu…`  

**Error:**
```
Access denied - path outside allowed directories". Which is really annoying because it means many tool calls instead of the first one succeeding.
```

---

## What Worked

**Tool:** `bash`  
**Input:** `(that I can't test as I can't seem to see building information):`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 15881311s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-08-11 19:29:24 UTC |
| Last seen | 2026-02-11 14:57:55 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: 403 from bash is not retryable; escalate to bash immediately (15881311s to recovery)._
