# Postmortem — permission_error

**Cluster:** `ext_0bbb3e4c`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-01-22 23:39:30 UTC |
| Recovery confirmed | 2025-02-26 20:38:13 UTC |
| Time to recovery | **3013123s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `server-github calls fail with "Error executing code: MCP error -32603: fetch is not defined" **Describe the bug**  When …`  

**Error:**
```
Error executing code: MCP error -32603: fetch is not defined
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3013123s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-01-22 23:39:30 UTC |
| Last seen | 2025-02-26 20:38:13 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: 403 from bash is not retryable; escalate to unknown immediately (3013123s to recovery)._
