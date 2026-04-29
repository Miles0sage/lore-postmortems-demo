# Postmortem — tool_execution_error

**Cluster:** `ext_f8dc784c`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-09-17 14:57:26 UTC |
| Recovery confirmed | 2025-10-19 14:23:00 UTC |
| Time to recovery | **2762734s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `[Bug] Claude Desktop: "Could not attach to MCP server {NAME OF MCP SERVER}" ## Description Everything is working properl…`  

**Error:**
```
message appears:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2762734s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-09-17 14:57:26 UTC |
| Last seen | 2025-10-19 14:23:00 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: tool_execution_error in read_file is recoverable via unknown in 2762734s — no human required._
