# Postmortem — compatibility_error

**Cluster:** `ext_1662bbd6`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-07 20:26:43 UTC |
| Recovery confirmed | 2026-04-17 20:49:46 UTC |
| Time to recovery | **865383s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Cline: Large output task fails with “YOLO mode task failed” error in Cline IDE ### Plugin Type  VSCode Extension  ### Cl…`  

**Error:**
```
instead of completing the request, indicating an issue with handling large responses.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 865383s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-07 20:26:43 UTC |
| Last seen | 2026-04-17 20:49:46 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: compatibility_error in bash is recoverable via unknown in 865383s — no human required._
