# Postmortem — timeout_error

**Cluster:** `ext_5a95c3fd`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-13 18:43:07 UTC |
| Recovery confirmed | 2026-04-17 09:37:50 UTC |
| Time to recovery | **312883s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG]  repeated stream idle timeout errors during large file writes ### Preflight Checklist  - [x] I have searched [exis…`  

**Error:**
```
API Error: Stream idle timeout - partial response received
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 312883s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-13 18:43:07 UTC |
| Last seen | 2026-04-17 09:37:50 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 312883s — no human required._
