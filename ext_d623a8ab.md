# Postmortem — network_error

**Cluster:** `ext_d623a8ab`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-05-21 23:34:30 UTC |
| Recovery confirmed | 2025-05-29 16:22:20 UTC |
| Time to recovery | **665270s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `Connection Issues with PostgreSQL MCP Server using SSL certificates ### Current Setup - Using @modelcontextprotocol/serv…`  

**Error:**
```
MCP -32603: unable to verify the first certificate.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 665270s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-05-21 23:34:30 UTC |
| Last seen | 2025-05-29 16:22:20 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in mcp_tool is recoverable via unknown in 665270s — no human required._
