# Postmortem — dependency_error

**Cluster:** `ext_2ba85fd7`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-04-25 06:44:54 UTC |
| Recovery confirmed | 2025-04-25 06:49:33 UTC |
| Time to recovery | **279s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `error code -32000 Bad Request: Server not initialized with StreamableHTTPServerTransport ## router of egg.js  ```js cons…`  

**Error:**
```
## router of egg.js  ```js const { McpServer } = require('@modelcontextprotocol/sdk/server/mcp.js'); const { StreamableHTTPServerTransport } = require('@modelcontextprotocol/sdk/server/streamableHttp.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 279s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-04-25 06:44:54 UTC |
| Last seen | 2025-04-25 06:49:33 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via unknown in 279s — no human required._
