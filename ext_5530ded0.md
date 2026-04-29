# Postmortem — timeout_error

**Cluster:** `ext_5530ded0`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-13 13:58:31 UTC |
| Recovery confirmed | 2025-05-29 16:20:34 UTC |
| Time to recovery | **6661323s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Connecting postgres with credentials stored in the env variable Is there any way I can connect to the postgres db with c…`  

**Error:**
```
Is there any way I can connect to the postgres db with credentials without hardcoding the credentials in the argument ?  Eg: In brave search mcp, the mcp server config looks like this:  ```json     "b
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 6661323s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-13 13:58:31 UTC |
| Last seen | 2025-05-29 16:20:34 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 6661323s — no human required._
