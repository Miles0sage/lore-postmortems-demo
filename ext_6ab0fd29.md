# Postmortem — resource_not_found

**Cluster:** `ext_6ab0fd29`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-09-21 09:01:50 UTC |
| Recovery confirmed | 2025-10-07 06:27:08 UTC |
| Time to recovery | **1373118s** |

---

## What Broke

**Tool:** `write_file`  
**Input:** `Odoo MCP: Query parameters in URI not properly handled, treated as model name # Bug Report: Odoo MCP Query Parameter Han…`  

**Error:**
```
"error": "<Fault warning -- UserError\n\nObject helpdesk.ticket?limit=5&order=create_date%20desc bestaat niet: ''>",
```

---

## What Worked

**Tool:** `write_file`  
**Input:** `Currently, users must use the basic URI without parameters and handle filtering/limiting in client code, which is less e…`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1373118s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-09-21 09:01:50 UTC |
| Last seen | 2025-10-07 06:27:08 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in write_file is recoverable via write_file in 1373118s — no human required._
