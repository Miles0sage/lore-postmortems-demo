# Postmortem — timeout_error

**Cluster:** `ext_80a58dbd`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-13 19:20:17 UTC |
| Recovery confirmed | 2026-04-17 09:37:43 UTC |
| Time to recovery | **310646s** |

---

## What Broke

**Tool:** `bash`  
**Input:** ``/ultraplan` remote session never reaches ExitPlanMode — two consecutive 90-min timeouts, remote container appears to ne…`  

**Error:**
```
to start, or session ID mismatch?)"*. Reproduced twice back-to-back with different session IDs, so it's not a transient glitch on a single session.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 310646s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-13 19:20:17 UTC |
| Last seen | 2026-04-17 09:37:43 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 310646s — no human required._
