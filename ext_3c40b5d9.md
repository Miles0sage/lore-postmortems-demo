# Postmortem — resource_not_found

**Cluster:** `ext_3c40b5d9`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-20 20:29:38 UTC |
| Recovery confirmed | 2026-03-22 13:05:25 UTC |
| Time to recovery | **10514147s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `execute_command reports success for failed commands (exit code validation missing) ### Plugin Type  VSCode Extension  ##…`  

**Error:**
```
appropriately
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 10514147s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-20 20:29:38 UTC |
| Last seen | 2026-03-22 13:05:25 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in bash is recoverable via unknown in 10514147s — no human required._
