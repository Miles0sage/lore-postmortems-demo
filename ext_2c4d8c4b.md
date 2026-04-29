# Postmortem — auth_error

**Cluster:** `ext_2c4d8c4b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-18 14:54:27 UTC |
| Recovery confirmed | 2026-04-18 14:58:06 UTC |
| Time to recovery | **219s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] Please run /login · API Error: 403 {"error":{"type":"forbidden","message":"Request not allowed"}} /login  Login OA…`  

**Error:**
```
Please run /login · API Error: 403 {"error":{"type":"forbidden","message":"Request not allowed"}} /login  Login OAuth error: Request failed with status code 403
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 219s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-18 14:54:27 UTC |
| Last seen | 2026-04-18 14:58:06 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 219s — no human required._
