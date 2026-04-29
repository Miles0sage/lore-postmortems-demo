# Postmortem — auth_error

**Cluster:** `ext_accbcdbb`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-16 15:05:43 UTC |
| Recovery confirmed | 2026-04-24 18:37:41 UTC |
| Time to recovery | **703918s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] Frequent mid-session 401 errors ### Preflight Checklist  - [x] I have searched [existing issues](https://github.co…`  

**Error:**
```
401 {"type":"error","error":{"type":"authentication_error","message":"Invalid authentication credentials"},"request_id":"req_011Ca7eMZaEWxrcefZLfmC8e"}
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 703918s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-16 15:05:43 UTC |
| Last seen | 2026-04-24 18:37:41 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 703918s — no human required._
