# Postmortem — dependency_error

**Cluster:** `ext_8deb6bde`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-11-26 18:23:23 UTC |
| Recovery confirmed | 2025-10-29 02:33:28 UTC |
| Time to recovery | **29059805s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `MCP Servers Don't Work with NVM ## Problem When using NVM (Node Version Manager), the standard installation and usage i…`  

**Error:**
```
## Problem When using NVM (Node Version Manager), the standard installation and usage instructions for MCP servers don't work. The app tries to use an incorrect Node and fails.  ## Workaround  1.
```

---

## What Worked

**Tool:** `bash`  
**Input:** `1. Avoid `npx`, install packages globally.`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 29059805s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-11-26 18:23:23 UTC |
| Last seen | 2025-10-29 02:33:28 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via bash in 29059805s — no human required._
