# Postmortem — dependency_error

**Cluster:** `ext_d8ac56f6`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-07-23 15:56:27 UTC |
| Recovery confirmed | 2025-07-27 14:46:07 UTC |
| Time to recovery | **341380s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `"Claude will return soon" after commands like "list_allowed_directories" Good time of the day to you!  Posted  this issu…`  

**Error:**
```
During MCP Command Execution
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 341380s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-07-23 15:56:27 UTC |
| Last seen | 2025-07-27 14:46:07 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via unknown in 341380s — no human required._
