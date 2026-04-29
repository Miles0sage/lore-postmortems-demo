# Postmortem — auth_error

**Cluster:** `ext_aa613f87`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-25 05:54:18 UTC |
| Recovery confirmed | 2026-03-28 09:13:43 UTC |
| Time to recovery | **271165s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] Cowork 403 "Request not allowed" on Pro plan - macOS - account not enabled ### Preflight Checklist  - [x] I have s…`  

**Error:**
```
on every attempt. Regular Claude chat works fine on the same account.
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

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 271165s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-25 05:54:18 UTC |
| Last seen | 2026-03-28 09:13:43 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 271165s — no human required._
