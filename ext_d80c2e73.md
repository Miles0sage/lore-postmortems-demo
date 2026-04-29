# Postmortem — mcp_server_error

**Cluster:** `ext_d80c2e73`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-12-22 23:02:46 UTC |
| Recovery confirmed | 2025-07-07 11:50:13 UTC |
| Time to recovery | **16980447s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Support "roots" in filesystem MCP server **Is your feature request related to a problem? Please describe.** Currently, …`  

**Error:**
```
**Is your feature request related to a problem? Please describe.** Currently, the filesystem server only allows a fixed set of allowed directories specified via an arg.  **Describe the solution you
```

---

## What Worked

**Tool:** `read_file`  
**Input:** `set of allowed directories specified via an arg.`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 16980447s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-12-22 23:02:46 UTC |
| Last seen | 2025-07-07 11:50:13 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in read_file is recoverable via read_file in 16980447s — no human required._
