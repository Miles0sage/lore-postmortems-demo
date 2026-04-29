# Postmortem — resource_not_found

**Cluster:** `ext_1d6e273e`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-20 11:34:47 UTC |
| Recovery confirmed | 2026-01-24 17:47:20 UTC |
| Time to recovery | **367953s** |

---

## What Broke

**Tool:** `write_file`  
**Input:** `Everything Server crashes when multiple clients reconnect **Describe the bug** The new `everything` server exits with an…`  

**Error:**
```
throw new Error('Not connected');
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 367953s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-20 11:34:47 UTC |
| Last seen | 2026-01-24 17:47:20 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in write_file is recoverable via unknown in 367953s — no human required._
