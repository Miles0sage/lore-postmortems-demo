# Postmortem — timeout_error

**Cluster:** `ext_f248e7ef`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-17 19:58:10 UTC |
| Recovery confirmed | 2026-04-21 09:37:40 UTC |
| Time to recovery | **308370s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `PreToolUse agent hook fails with "Messages are required for agent hooks. This is a bug." ## Summary  A `PreToolUse` agen…`  

**Error:**
```
message text itself flags this as a bug in Claude Code's runtime.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 308370s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-17 19:58:10 UTC |
| Last seen | 2026-04-21 09:37:40 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 308370s — no human required._
