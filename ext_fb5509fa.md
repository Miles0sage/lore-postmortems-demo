# Postmortem — timeout_error

**Cluster:** `ext_fb5509fa`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-10-30 03:33:03 UTC |
| Recovery confirmed | 2025-11-25 22:07:22 UTC |
| Time to recovery | **2313259s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Request to add an MCP server: gurddy,A Match MCP server #### INFO A comprehensive Model Context Protocol (MCP) server fo…`  

**Error:**
```
#### INFO A comprehensive Model Context Protocol (MCP) server for solving Constraint Satisfaction Problems (CSP), Linear Programming (LP), Minimax optimization, and SciPy-powered advanced optimization
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2313259s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-10-30 03:33:03 UTC |
| Last seen | 2025-11-25 22:07:22 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 2313259s — no human required._
