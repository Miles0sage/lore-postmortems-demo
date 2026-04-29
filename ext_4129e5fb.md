# Postmortem — timeout_error

**Cluster:** `ext_4129e5fb`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-04 01:11:45 UTC |
| Recovery confirmed | 2026-03-13 12:52:14 UTC |
| Time to recovery | **819629s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `[3.69.0 ]A private MCP service that was working normally suddenly failed to connect to Cline. ### Plugin Type  VSCode Ex…`  

**Error:**
```
ERROR Transport error for "transfer-server":
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 819629s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-04 01:11:45 UTC |
| Last seen | 2026-03-13 12:52:14 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in mcp_tool is recoverable via unknown in 819629s — no human required._
