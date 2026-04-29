# Postmortem — resource_not_found

**Cluster:** `ext_d37ff95f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-04 16:39:39 UTC |
| Recovery confirmed | 2025-11-05 12:14:26 UTC |
| Time to recovery | **70487s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Cline CLI Error ### Plugin Type  CLI  ### Cline Version  CLI Version 1.0.4  ### What happened?  I can get the version ou…`  

**Error:**
```
failed to start new instance: failed to start instance: operation failed to after 12 attempts: instance not found in registry: database not available
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 70487s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-04 16:39:39 UTC |
| Last seen | 2025-11-05 12:14:26 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in bash is recoverable via unknown in 70487s — no human required._
