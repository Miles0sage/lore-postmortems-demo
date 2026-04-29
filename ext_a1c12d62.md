# Postmortem — timeout_error

**Cluster:** `ext_a1c12d62`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-01-28 05:08:43 UTC |
| Recovery confirmed | 2025-06-12 13:49:18 UTC |
| Time to recovery | **11695235s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `MCP Obsidian Configuration Issue: Invalid Server Connection and JSON Configuration Fix written by claude sonnet.  **Desc…`  

**Error:**
```
message: "Tool 'markdown' not found"
```

---

## What Worked

**Tool:** `bash`  
**Input:** `has been verified to work with both local and iCloud-based Obsidian vaults`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 11695235s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-01-28 05:08:43 UTC |
| Last seen | 2025-06-12 13:49:18 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via bash in 11695235s — no human required._
