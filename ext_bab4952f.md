# Postmortem — schema_validation_error

**Cluster:** `ext_bab4952f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-21 10:17:33 UTC |
| Recovery confirmed | 2026-04-20 18:57:18 UTC |
| Time to recovery | **2623185s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `server-gitlab: tools not registered due to zod v3/v4 dependency conflict ## Bug  `server-gitlab` shows as "Connected" in…`  

**Error:**
```
## Bug  `server-gitlab` shows as "Connected" in Claude Code (`claude mcp list`) but **no tools are registered**. The `tools/list` MCP response returns tools with empty `inputSchema: {}` objects, which
```

---

## What Worked

**Tool:** `bash`  
**Input:** `Downgrade the root zod in the npx cache:`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2623185s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-21 10:17:33 UTC |
| Last seen | 2026-04-20 18:57:18 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: schema_validation_error in bash is recoverable via bash in 2623185s — no human required._
