# Postmortem — mcp_server_error

**Cluster:** `ext_1f67f2b3`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-10-03 23:51:57 UTC |
| Recovery confirmed | 2026-01-11 01:26:13 UTC |
| Time to recovery | **8559256s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** ``server/everything` reports error when requesting tools **Describe the bug**  Attempting to make a request to the `every…`  

**Error:**
```
data: {"jsonrpc":"2.0","id":1,"error":{"code":-32603,"message":"Cannot read properties of undefined (reading 'roots')"}}
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 8559256s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-10-03 23:51:57 UTC |
| Last seen | 2026-01-11 01:26:13 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in read_file is recoverable via unknown in 8559256s — no human required._
