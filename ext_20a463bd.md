# Postmortem — permission_error

**Cluster:** `ext_20a463bd`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-07-26 18:38:21 UTC |
| Recovery confirmed | 2025-08-24 03:04:20 UTC |
| Time to recovery | **2449559s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Filesystem server fails with directory paths containing spaces  **Describe the bug** MCP filesystem server fails to prop…`  

**Error:**
```
The issue appears to be in argument parsing where spaces in paths are not properly handled
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2449559s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-07-26 18:38:21 UTC |
| Last seen | 2025-08-24 03:04:20 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: 403 from bash is not retryable; escalate to unknown immediately (2449559s to recovery)._
