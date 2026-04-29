# Postmortem — mcp_server_error

**Cluster:** `ext_35f6d8ad`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-12-16 09:35:19 UTC |
| Recovery confirmed | 2025-05-29 16:18:11 UTC |
| Time to recovery | **14193772s** |

---

## What Broke

**Tool:** `write_file`  
**Input:** `Gitlab server - Invalid arguments  ## Issue Description  When attempting to interact with GitLab's API through the int…`  

**Error:**
```
MCP error -32603: Invalid arguments: fork: Required
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 14193772s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-12-16 09:35:19 UTC |
| Last seen | 2025-05-29 16:18:11 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in write_file is recoverable via unknown in 14193772s — no human required._
