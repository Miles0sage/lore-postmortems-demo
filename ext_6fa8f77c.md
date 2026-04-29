# Postmortem — network_error

**Cluster:** `ext_6fa8f77c`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-08-01 06:20:51 UTC |
| Recovery confirmed | 2025-08-01 08:45:11 UTC |
| Time to recovery | **8660s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `MCP-fetch server exits immediately after first response instead of maintaining persistent stdio connection **Bug Descrip…`  

**Error:**
```
await server.run(read_stream, write_stream, options, raise_exceptions=True)
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 8660s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-08-01 06:20:51 UTC |
| Last seen | 2025-08-01 08:45:11 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 8660s — no human required._
