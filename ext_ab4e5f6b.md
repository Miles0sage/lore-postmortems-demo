# Postmortem — mcp_server_error

**Cluster:** `ext_ab4e5f6b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-11-28 08:17:29 UTC |
| Recovery confirmed | 2025-05-29 16:12:12 UTC |
| Time to recovery | **15753283s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `Could Not Attach to MCP Server Postgres I'm encountering an issue when trying to add an MCP Postgres server to the chat …`  

**Error:**
```
message displayed is:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 15753283s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-11-28 08:17:29 UTC |
| Last seen | 2025-05-29 16:12:12 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in mcp_tool is recoverable via unknown in 15753283s — no human required._
