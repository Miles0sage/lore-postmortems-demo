# Postmortem — timeout_error

**Cluster:** `ext_1f1e987e`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-15 12:44:09 UTC |
| Recovery confirmed | 2026-04-15 12:45:01 UTC |
| Time to recovery | **52s** |

---

## What Broke

**Tool:** `edit_file`  
**Input:** `API stream timeout causes silent failure - no retry, no user notification ## Bug Description  When the Anthropic API tim…`  

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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 52s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-15 12:44:09 UTC |
| Last seen | 2026-04-15 12:45:01 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in edit_file is recoverable via unknown in 52s — no human required._
