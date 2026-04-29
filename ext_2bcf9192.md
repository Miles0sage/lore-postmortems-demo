# Postmortem — auth_error

**Cluster:** `ext_2bcf9192`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-25 10:07:00 UTC |
| Recovery confirmed | 2026-03-01 09:13:41 UTC |
| Time to recovery | **342401s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] Failed to authenticate. API Error: 403 {"error":{"type":"forbidden","message":"Request not allowed"}} ### Prefligh…`  

**Error:**
```
403 {"error":{"type":"forbidden","message":"Request not allowed"}}
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 342401s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-25 10:07:00 UTC |
| Last seen | 2026-03-01 09:13:41 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 342401s — no human required._
