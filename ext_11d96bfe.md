# Postmortem — network_error

**Cluster:** `ext_11d96bfe`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-06-19 02:58:35 UTC |
| Recovery confirmed | 2025-06-20 15:10:31 UTC |
| Time to recovery | **130316s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Puppeteer MCP server cannot connect to localhost **Describe the bug** If I ask Claude Code to navigate to Google's homep…`  

**Error:**
```
Error: MCP error -32603: net::ERR_CONNECTION_REFUSED at http://localhost:4000
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 130316s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-06-19 02:58:35 UTC |
| Last seen | 2025-06-20 15:10:31 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 130316s — no human required._
