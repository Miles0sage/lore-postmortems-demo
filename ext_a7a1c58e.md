# Postmortem — mcp_server_error

**Cluster:** `ext_a7a1c58e`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-15 14:46:04 UTC |
| Recovery confirmed | 2026-04-19 09:23:40 UTC |
| Time to recovery | **326256s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `API Error: 500 {"type":"error","error":{"type":"api_error","... **Bug Description** API Error: 500 {"type":"error","erro…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/julien.beghain.txsst/.local/share/claude/versions/2.1.109 (expected in multi-process scenarios)\n    at yU_ (/$bunfs/root/src/entrypoint
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 326256s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-15 14:46:04 UTC |
| Last seen | 2026-04-19 09:23:40 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: mcp_server_error in bash is recoverable via unknown in 326256s — no human required._
