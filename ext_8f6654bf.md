# Postmortem — compatibility_error

**Cluster:** `ext_8f6654bf`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-18 22:34:18 UTC |
| Recovery confirmed | 2026-02-12 20:51:17 UTC |
| Time to recovery | **7424219s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Bad Request Error [400] ### What happened? /crea I'm running into this error after the latest update, is anyone facing t…`  

**Error:**
```
after the latest update, is anyone facing the same issue?
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 7424219s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-18 22:34:18 UTC |
| Last seen | 2026-02-12 20:51:17 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: compatibility_error in bash is recoverable via unknown in 7424219s — no human required._
