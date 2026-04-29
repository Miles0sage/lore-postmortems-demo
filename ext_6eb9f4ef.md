# Postmortem — resource_not_found

**Cluster:** `ext_6eb9f4ef`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-24 21:03:56 UTC |
| Recovery confirmed | 2025-08-15 23:24:40 UTC |
| Time to recovery | **12450044s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Postgresql server, code -32601 Hello  I have sucessfully established connection to postgresql from Claude desktop but a …`  

**Error:**
```
2025-03-24T20:52:37.545Z [postgres] [info] Message from server: {"jsonrpc":"2.0","id":6,"error":{"code":-32601,"message":"Method not found"}}
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 12450044s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-24 21:03:56 UTC |
| Last seen | 2025-08-15 23:24:40 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in bash is recoverable via unknown in 12450044s — no human required._
