# Postmortem — network_error

**Cluster:** `ext_b203be4b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-07-14 10:29:24 UTC |
| Recovery confirmed | 2025-08-05 09:21:18 UTC |
| Time to recovery | **1896714s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `I can't connect to some MCP server via Claude Clode CLI Error stack: McpError: MCP error -32000: Connection closed I am …`  

**Error:**
```
MCP error -32000: Connection closed",
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1896714s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-07-14 10:29:24 UTC |
| Last seen | 2025-08-05 09:21:18 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in read_file is recoverable via unknown in 1896714s — no human required._
