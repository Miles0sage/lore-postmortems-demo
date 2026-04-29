# Postmortem — resource_not_found

**Cluster:** `ext_8000aaa8`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-02-14 19:55:22 UTC |
| Recovery confirmed | 2025-02-14 20:08:24 UTC |
| Time to recovery | **782s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `"resources/list" method missing - blocking usage in Claude Desktop **Describe the bug** The server is missing the "resou…`  

**Error:**
```
[info] Message from server: {"jsonrpc":"2.0","id":1,"error":{"code":-32601,"message":"Method not found"}}
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 782s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-02-14 19:55:22 UTC |
| Last seen | 2025-02-14 20:08:24 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in read_file is recoverable via unknown in 782s — no human required._
