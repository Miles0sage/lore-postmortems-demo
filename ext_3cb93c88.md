# Postmortem — resource_not_found

**Cluster:** `ext_3cb93c88`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-12-05 15:47:15 UTC |
| Recovery confirmed | 2026-04-20 10:36:30 UTC |
| Time to recovery | **11731755s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Cline CLI - showTaskWithId: rpc error: code = Internal desc = Task not found ### Plugin Type  CLI  ### Cline Version  3.…`  

**Error:**
```
Error: failed to resume task 1764940901829: Failed to reinitialize task 1764940901829: failed to get latest showTaskWithId: rpc error: code = Internal desc = Task not found
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 11731755s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-12-05 15:47:15 UTC |
| Last seen | 2026-04-20 10:36:30 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via unknown in 11731755s — no human required._
