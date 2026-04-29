# Postmortem — agent_loop

**Cluster:** `ext_6a5f0dd0`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-05-17 15:21:49 UTC |
| Recovery confirmed | 2025-08-09 01:58:45 UTC |
| Time to recovery | **7209416s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `When using the filesystem MCP server on Windows, the error "Parent directory does not exist" always occurs. I have alrea…`  

**Error:**
```
"Parent directory does not exist" always occurs.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 7209416s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-05-17 15:21:49 UTC |
| Last seen | 2025-08-09 01:58:45 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: agent_loop in read_file is recoverable via unknown in 7209416s — no human required._
