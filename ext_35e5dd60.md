# Postmortem — dependency_error

**Cluster:** `ext_35e5dd60`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-03 09:57:07 UTC |
| Recovery confirmed | 2026-04-09 21:05:45 UTC |
| Time to recovery | **13604918s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Access denied when multiple projects are opened ### Plugin Type  JetBrains Plugin  ### Cline Version  1.1.1  ### What ha…`  

**Error:**
```
popups with following error message:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 13604918s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-03 09:57:07 UTC |
| Last seen | 2026-04-09 21:05:45 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in read_file is recoverable via unknown in 13604918s — no human required._
