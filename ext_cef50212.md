# Postmortem — resource_not_found

**Cluster:** `ext_cef50212`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-05-08 07:33:39 UTC |
| Recovery confirmed | 2025-06-20 06:18:02 UTC |
| Time to recovery | **3710663s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `ModuleNotFoundError: No module named 'mcp.server.streamable_http' Hello, when I uv add mcp, it works fine. But when I bu…`  

**Error:**
```
message "ModuleNotFoundError: No module named 'mcp.server.streamable_http'" when I execute from mcp.server.streamable_http import (
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3710663s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-05-08 07:33:39 UTC |
| Last seen | 2025-06-20 06:18:02 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in bash is recoverable via unknown in 3710663s — no human required._
