# Postmortem — network_error

**Cluster:** `ext_6fa79fb2`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-10-03 14:14:28 UTC |
| Recovery confirmed | 2026-02-06 13:38:32 UTC |
| Time to recovery | **10884244s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `MCP Filesystem Server crashes when configured path is unavailable **Describe the bug** The MCP Filesystem server crashes…`  

**Error:**
```
**Expected behavior**
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 10884244s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-10-03 14:14:28 UTC |
| Last seen | 2026-02-06 13:38:32 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in read_file is recoverable via unknown in 10884244s — no human required._
