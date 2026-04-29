# Postmortem — network_error

**Cluster:** `ext_b42cbda4`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-27 13:46:19 UTC |
| Recovery confirmed | 2025-04-19 21:50:25 UTC |
| Time to recovery | **2016246s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `GitHub MCP Server Fails to Start: 'npx' Command Error and Connection Closed (-32000) **Describe the bug** The MCP server…`  

**Error:**
```
message shows garbled text followed by "MCP error -32000: Connection closed." This issue occurs when attempting to use the `npx` command to start the GitHub MCP server.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2016246s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-27 13:46:19 UTC |
| Last seen | 2025-04-19 21:50:25 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 2016246s — no human required._
