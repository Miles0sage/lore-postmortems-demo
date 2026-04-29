# Postmortem — resource_not_found

**Cluster:** `ext_59d1f8d9`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-08 17:37:30 UTC |
| Recovery confirmed | 2026-04-09 21:15:14 UTC |
| Time to recovery | **13145864s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Support random GLIBC versions ### Plugin Type  JetBrains Plugin  ### Cline Version  1.1.3  ### What happened?  OEL 8. Cl…`  

**Error:**
```
Failed to initialize SQLite database at /home/user/.cline/data/locks.db: Error: /lib64/libm.so.6: version GLIBC_2.29' not found (required by /scratch/.IntelliJIdea/plugins/cline/core/1.1.3/binaries/li
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 13145864s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-08 17:37:30 UTC |
| Last seen | 2026-04-09 21:15:14 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via unknown in 13145864s — no human required._
