# Postmortem — tool_execution_error

**Cluster:** `ext_ff195e5e`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-26 07:45:49 UTC |
| Recovery confirmed | 2026-02-16 20:39:50 UTC |
| Time to recovery | **7131241s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `API request is failing ### Plugin Type  VSCode Extension  ### Cline Version  Cline v3.37.1  ### What happened?  Receivin…`  

**Error:**
```
irrespective of any prompt:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 7131241s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-26 07:45:49 UTC |
| Last seen | 2026-02-16 20:39:50 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: tool_execution_error in mcp_tool is recoverable via unknown in 7131241s — no human required._
