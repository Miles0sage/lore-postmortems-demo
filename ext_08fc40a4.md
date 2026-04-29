# Postmortem — auth_error

**Cluster:** `ext_08fc40a4`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-09-02 02:57:34 UTC |
| Recovery confirmed | 2026-02-16 20:37:26 UTC |
| Time to recovery | **14492392s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `I am getting this 403 forbidden error with every llm including claude ### What happened?  API Request Failed  $0.0000  4…`  

**Error:**
```
### Steps to reproduce
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 14492392s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-09-02 02:57:34 UTC |
| Last seen | 2026-02-16 20:37:26 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 14492392s — no human required._
