# Postmortem — dependency_error

**Cluster:** `ext_4d61d82d`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-10-29 10:28:41 UTC |
| Recovery confirmed | 2025-11-08 03:04:03 UTC |
| Time to recovery | **837322s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `server: filesystem test are failing when trying to build inside docker ``` > [ 9/22] RUN git clone --depth 1 https://git…`  

**Error:**
```
27.80 npm error code 2
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 837322s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-10-29 10:28:41 UTC |
| Last seen | 2025-11-08 03:04:03 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via unknown in 837322s — no human required._
