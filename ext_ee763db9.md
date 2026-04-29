# Postmortem — general_failure

**Cluster:** `ext_ee763db9`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-08-15 18:42:23 UTC |
| Recovery confirmed | 2025-08-28 17:04:30 UTC |
| Time to recovery | **1117327s** |

---

## What Broke

**Tool:** `mcp_tool`  
**Input:** `Support roots in the everything server Can we add roots to the everything server?`  

**Error:**
```
Can we add roots to the everything server?
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1117327s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-08-15 18:42:23 UTC |
| Last seen | 2025-08-28 17:04:30 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: general_failure in mcp_tool is recoverable via unknown in 1117327s — no human required._
