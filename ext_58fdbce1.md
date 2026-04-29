# Postmortem — resource_not_found

**Cluster:** `ext_58fdbce1`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-07-23 13:25:48 UTC |
| Recovery confirmed | 2025-07-23 18:30:25 UTC |
| Time to recovery | **18277s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Claude Desktop not passing required parameters to MCP filesystem server tools The MCP filesystem server appears to be wo…`  

**Error:**
```
2025-07-23T13:13:02.813Z [info] [filesystem] Message from server: {"jsonrpc":"2.0","id":5,"error":{"code":-32601,"message":"Method not found"}}
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 18277s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-07-23 13:25:48 UTC |
| Last seen | 2025-07-23 18:30:25 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via unknown in 18277s — no human required._
