# Postmortem — permission_error

**Cluster:** `ext_a2d0da9c`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-07-17 08:10:20 UTC |
| Recovery confirmed | 2025-07-17 10:11:40 UTC |
| Time to recovery | **7280s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Windows filesystem server blocks subdirectory access despite C:\ root configuration Windows filesystem server blocks sub…`  

**Error:**
```
Error: Access denied - path outside allowed directories: C:\Users not in C:\
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 7280s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-07-17 08:10:20 UTC |
| Last seen | 2025-07-17 10:11:40 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: 403 from bash is not retryable; escalate to unknown immediately (7280s to recovery)._
