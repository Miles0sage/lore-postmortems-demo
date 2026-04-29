# Postmortem — permission_error

**Cluster:** `ext_2dd56c88`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-12-27 17:53:08 UTC |
| Recovery confirmed | 2025-04-19 22:06:51 UTC |
| Time to recovery | **9778423s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `GitHub mcp file creation error: Failed to call tool create_or_update_file: Error: MCP error 32604: I get this error when…`  

**Error:**
```
when Claude Desktop is trying to create files to my repo. I created this private repo in the same chat earlier.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 9778423s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-12-27 17:53:08 UTC |
| Last seen | 2025-04-19 22:06:51 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: 403 from read_file is not retryable; escalate to unknown immediately (9778423s to recovery)._
