# Postmortem — auth_error

**Cluster:** `ext_3f3bdb23`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-22 17:58:17 UTC |
| Recovery confirmed | 2026-04-21 10:37:43 UTC |
| Time to recovery | **2565566s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `[BUG] v2.1.81 - multiple parallel agents cause 401 auth issue ### Preflight Checklist  - [x] I have searched [existing i…`  

**Error:**
```
⎿  Referenced file ../../../docs/00-progress.md
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2565566s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-22 17:58:17 UTC |
| Last seen | 2026-04-21 10:37:43 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 2565566s — no human required._
