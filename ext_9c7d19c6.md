# Postmortem — mcp_server_error

**Cluster:** `ext_9c7d19c6`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-09-02 12:30:19 UTC |
| Recovery confirmed | 2025-09-02 12:33:45 UTC |
| Time to recovery | **206s** |

---

## What Broke

**Tool:** `write_file`  
**Input:** `MCP Index Server List Operation Missing Instructions - Inconsistent Results created in error`  

**Error:**
```
created in error
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 206s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-09-02 12:30:19 UTC |
| Last seen | 2025-09-02 12:33:45 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in write_file is recoverable via unknown in 206s — no human required._
