# Postmortem — auth_error

**Cluster:** `ext_c56d437c`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-09-02 03:01:09 UTC |
| Recovery confirmed | 2026-02-16 20:37:04 UTC |
| Time to recovery | **14492155s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `x-ai/grok-code-fast1 api request failed 403 ### What happened? It was working fine before the issue occurred, but sudden…`  

**Error:**
```
on all tasks.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 14492155s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-09-02 03:01:09 UTC |
| Last seen | 2026-02-16 20:37:04 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 14492155s — no human required._
