# Postmortem — permission_error

**Cluster:** `ext_e18f45cf`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-24 06:32:13 UTC |
| Recovery confirmed | 2025-08-09 01:58:36 UTC |
| Time to recovery | **11906783s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `server-filesystem directory volume char with diff form **Describe the bug** In **windows OS**, the _Allowed directories_…`  

**Error:**
```
returns as :
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 11906783s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-24 06:32:13 UTC |
| Last seen | 2025-08-09 01:58:36 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: 403 from read_file is not retryable; escalate to unknown immediately (11906783s to recovery)._
