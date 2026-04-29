# Postmortem — resource_not_found

**Cluster:** `ext_298dc0d2`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-03 04:08:24 UTC |
| Recovery confirmed | 2025-04-19 21:51:31 UTC |
| Time to recovery | **4124587s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Error using GitHub MCP Server 'create_issue' tool **Describe the bug** When I try to use the GitHub MCP Server `create_i…`  

**Error:**
```
`MCP error -32603: Not Found: Resource not found: Not Found.  `
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4124587s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-03 04:08:24 UTC |
| Last seen | 2025-04-19 21:51:31 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in bash is recoverable via unknown in 4124587s — no human required._
