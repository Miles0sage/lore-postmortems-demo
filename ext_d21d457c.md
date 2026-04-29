# Postmortem — auth_error

**Cluster:** `ext_d21d457c`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-27 10:07:23 UTC |
| Recovery confirmed | 2025-12-17 19:47:08 UTC |
| Time to recovery | **1762785s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `CLI fails with "database not available" error on Node.js 25 ### Plugin Type  CLI  ### Cline Version  Cline CLI Version: …`  

**Error:**
```
Error: failed to start auth instance: failed to start instance: operation failed to after 12 attempts: instance not found in registry: database not available
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1762785s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-27 10:07:23 UTC |
| Last seen | 2025-12-17 19:47:08 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 1762785s — no human required._
