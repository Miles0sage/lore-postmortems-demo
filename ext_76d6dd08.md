# Postmortem — auth_error

**Cluster:** `ext_76d6dd08`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-22 13:17:46 UTC |
| Recovery confirmed | 2026-04-21 22:20:42 UTC |
| Time to recovery | **2624576s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Session resume after 403 retry breaks parentUuid chain, losing entire conversation history ## Bug Description  When an A…`  

**Error:**
```
L53702 [assistant] 403 error
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2624576s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-22 13:17:46 UTC |
| Last seen | 2026-04-21 22:20:42 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 2624576s — no human required._
