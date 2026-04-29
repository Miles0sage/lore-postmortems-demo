# Postmortem — schema_validation_error

**Cluster:** `ext_05ad4f97`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-13 07:37:04 UTC |
| Recovery confirmed | 2026-01-24 10:05:50 UTC |
| Time to recovery | **959326s** |

---

## What Broke

**Tool:** `write_file`  
**Input:** `server-memory: Output schema has additionalProperties: false but response includes 'type' field ## Description When usin…`  

**Error:**
```
RuntimeError: Invalid structured content returned by tool search_nodes: Additional properties are not allowed ('type' was unexpected)
```

---

## What Worked

**Tool:** `write_file`  
**Input:** `The `search_nodes` tool's output schema declares `additionalProperties: false` for entity items, but the actual response…`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 959326s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-13 07:37:04 UTC |
| Last seen | 2026-01-24 10:05:50 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: schema_validation_error in write_file is recoverable via write_file in 959326s — no human required._
