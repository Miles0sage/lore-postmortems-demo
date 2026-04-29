# Postmortem — auth_error

**Cluster:** `ext_f831b83a`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-07-28 16:57:19 UTC |
| Recovery confirmed | 2025-08-04 03:11:50 UTC |
| Time to recovery | **555271s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `Intercom MCP Server OAuth redirect URI not allowlisted **Describe the bug** The Intercom MCP server fails to authenticat…`  

**Error:**
```
- Error 401: invalid_token
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 555271s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-07-28 16:57:19 UTC |
| Last seen | 2025-08-04 03:11:50 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in mcp_tool is recoverable via unknown in 555271s — no human required._
