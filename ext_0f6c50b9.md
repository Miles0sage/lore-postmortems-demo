# Postmortem — auth_error

**Cluster:** `ext_0f6c50b9`  
**Severity:** LOW (n_observations: 4)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-25 09:18:24 UTC |
| Recovery confirmed | 2026-01-25 09:18:57 UTC |
| Time to recovery | **33s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Claude 4.5 Opus - 401`  

**Error:**
```
Error: Claude 4.5 Opus - 401
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

This failure pattern has been observed **4 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 33s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-25 09:18:24 UTC |
| Last seen | 2026-01-25 09:18:57 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 33s — no human required._
