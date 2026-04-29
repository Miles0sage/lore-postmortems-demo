# Postmortem — resource_not_found

**Cluster:** `ext_a70f2ed1`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-09-30 09:22:48 UTC |
| Recovery confirmed | 2025-10-29 01:56:59 UTC |
| Time to recovery | **2478851s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `WSL path conversion bug in v2025.8.18+ causes ENOENT errors When running @modelcontextprotocol/server-filesystem through…`  

**Error:**
```
Error accessing directory C:\Users\username\folder: Error: ENOENT: no such file or directory, stat 'C:\Users\username\folder'
```

---

## What Worked

**Tool:** `read_file`  
**Input:** `Pin to version 2025.7.29**`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2478851s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-09-30 09:22:48 UTC |
| Last seen | 2025-10-29 01:56:59 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via read_file in 2478851s — no human required._
