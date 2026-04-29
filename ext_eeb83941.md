# Postmortem — mcp_server_error

**Cluster:** `ext_eeb83941`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-12-20 00:42:25 UTC |
| Recovery confirmed | 2025-05-29 16:28:31 UTC |
| Time to recovery | **13880766s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Error: GOOGLE_MAPS_API_KEY environment variable is not set **Describe the bug** Cannot connect to Google maps MCP serve…`  

**Error:**
```
**Describe the bug** Cannot connect to Google maps MCP server. When I try to run command manually:  `npx -y @modelcontextprotocol/server-google-maps` I am getting  "GOOGLE_MAPS_API_KEY environment va
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 13880766s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-12-20 00:42:25 UTC |
| Last seen | 2025-05-29 16:28:31 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in bash is recoverable via unknown in 13880766s — no human required._
