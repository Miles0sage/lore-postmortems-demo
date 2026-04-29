# Postmortem — auth_error

**Cluster:** `ext_fa907cc7`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-12-15 19:43:25 UTC |
| Recovery confirmed | 2025-12-19 21:42:01 UTC |
| Time to recovery | **352716s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Unable To Cline Auth with cline provider in Cline CLI ### Plugin Type  CLI  ### Cline Version  Cline CLI Version:  1.0.8…`  

**Error:**
```
[VERBOSE] Server verification failed: failed to get latest getUserCredits: rpc error: code = Internal desc = Failed to fetch user credits data
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 352716s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-12-15 19:43:25 UTC |
| Last seen | 2025-12-19 21:42:01 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 352716s — no human required._
