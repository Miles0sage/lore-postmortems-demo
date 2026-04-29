# Postmortem — dependency_error

**Cluster:** `ext_1a5a6da7`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-12-07 20:05:07 UTC |
| Recovery confirmed | 2025-05-29 16:18:03 UTC |
| Time to recovery | **14933576s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Unable to use mcp-server-sqlite, but found a solution  **Describe the bug** when I add the sqlite mcp server to Claude …`  

**Error:**
```
that kept me from using it:
```

---

## What Worked

**Tool:** `bash`  
**Input:** `that I found is to run`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 14933576s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-12-07 20:05:07 UTC |
| Last seen | 2025-05-29 16:18:03 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via bash in 14933576s — no human required._
