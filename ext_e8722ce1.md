# Postmortem — schema_validation_error

**Cluster:** `ext_e8722ce1`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-04-26 10:07:58 UTC |
| Recovery confirmed | 2025-05-29 16:21:42 UTC |
| Time to recovery | **2873624s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Build Failure: Missing `zod` dependency in multiple packages (`filesystem`, `gitlab`, `redis`) **Problem:**  When runnin…`  

**Error:**
```
error TS2307: Cannot find module 'zod' or its corresponding type declarations.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2873624s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-04-26 10:07:58 UTC |
| Last seen | 2025-05-29 16:21:42 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: schema_validation_error in bash is recoverable via unknown in 2873624s — no human required._
