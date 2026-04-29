# Postmortem — auth_error

**Cluster:** `ext_8ce2475e`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-21 13:29:19 UTC |
| Recovery confirmed | 2025-11-23 00:54:54 UTC |
| Time to recovery | **127535s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `mcp server error ### Plugin Type  VSCode Extension  ### Cline Version  3.38.1  ### What happened?  I've configured an MC…`  

**Error:**
```
Error POSTing to endpoint (HTTP 404): {"jsonrpc":"2.0","error":{"code":-32601,"message":"Method not found","data":"api not found"},"id":3}
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 127535s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-21 13:29:19 UTC |
| Last seen | 2025-11-23 00:54:54 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in mcp_tool is recoverable via unknown in 127535s — no human required._
