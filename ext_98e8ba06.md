# Postmortem — schema_validation_error

**Cluster:** `ext_98e8ba06`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-19 22:30:45 UTC |
| Recovery confirmed | 2026-03-15 15:35:32 UTC |
| Time to recovery | **2048687s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `mcp-server-fetch: Server crashes on any malformed input due to raise_exceptions=True **Describe the bug**  mcp-server-fe…`  

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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2048687s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-19 22:30:45 UTC |
| Last seen | 2026-03-15 15:35:32 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: schema_validation_error in read_file is recoverable via unknown in 2048687s — no human required._
