# Postmortem — auth_error

**Cluster:** `ext_fe1727a3`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-25 15:23:17 UTC |
| Recovery confirmed | 2026-03-29 09:18:43 UTC |
| Time to recovery | **323726s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] Cowork returns 403 on macOS 26.3.1 but works on macOS 26.3 ### Preflight Checklist  - [x] I have searched [existin…`  

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

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 323726s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-25 15:23:17 UTC |
| Last seen | 2026-03-29 09:18:43 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 323726s — no human required._
