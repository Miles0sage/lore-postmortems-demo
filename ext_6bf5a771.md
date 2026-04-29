# Postmortem — dependency_error

**Cluster:** `ext_6bf5a771`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-06-26 08:46:08 UTC |
| Recovery confirmed | 2026-01-15 22:23:59 UTC |
| Time to recovery | **17588271s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Impossible to use cline always the error "[ERROR] Failed to process response: The pending stream has been canceled (caus…`  

**Error:**
```
`[ERROR] Failed to process response: The pending stream has been canceled (caused by: )`
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 17588271s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-06-26 08:46:08 UTC |
| Last seen | 2026-01-15 22:23:59 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via unknown in 17588271s — no human required._
