# Postmortem — dependency_error

**Cluster:** `ext_a04d7b7a`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-25 16:25:26 UTC |
| Recovery confirmed | 2026-04-17 14:35:08 UTC |
| Time to recovery | **1980582s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[WIndows Specific]Cline CLI: Getting "Error Spawn EINVAL..." when trying to open Cline CLI ### Plugin Type  CLI  ### Cli…`  

**Error:**
```
when trying to open CLine CLI in terminal
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1980582s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-25 16:25:26 UTC |
| Last seen | 2026-04-17 14:35:08 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via unknown in 1980582s — no human required._
