# Postmortem — network_error

**Cluster:** `ext_1de2a7e1`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-04-10 14:37:22 UTC |
| Recovery confirmed | 2025-05-29 16:21:17 UTC |
| Time to recovery | **4239835s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `MCP redis: Server disconnected **Describe the bug** The `index.js` file in `@modelcontextprotocol/server-redis` opens in…`  

**Error:**
```
2025-04-10T14:18:24.259Z [redis] [info] Server transport closed unexpectedly, this is likely due to the process exiting early. If you are developing this MCP server you can add output to stderr (i.e.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4239835s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-04-10 14:37:22 UTC |
| Last seen | 2025-05-29 16:21:17 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in read_file is recoverable via unknown in 4239835s — no human required._
