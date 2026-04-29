# Postmortem — dependency_error

**Cluster:** `ext_679d78dc`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-05-07 02:50:04 UTC |
| Recovery confirmed | 2025-05-29 16:21:56 UTC |
| Time to recovery | **1949512s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Cannot run postgresql server I tried to run the postgresql server but I'm getting this error when trying to start it:  `…`  

**Error:**
```
when trying to start it:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1949512s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-05-07 02:50:04 UTC |
| Last seen | 2025-05-29 16:21:56 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via unknown in 1949512s — no human required._
