# Postmortem — timeout_error

**Cluster:** `ext_2df61f0f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-09 11:45:11 UTC |
| Recovery confirmed | 2026-04-07 22:18:10 UTC |
| Time to recovery | **2543579s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Rating prompt conflicts with numbered option lists in chat **Bug Description** this was an accidental rating - BUT…`  

**Error:**
```
[{"error":"Error: 1P event logging: 44 events failed to export (code=ECONNABORTED, timeout of 10000ms exceeded)\n    at queueFailedEvents (/$bunfs/root/src/entrypoints/cli.js:6764:2694)\n    at async
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2543579s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-09 11:45:11 UTC |
| Last seen | 2026-04-07 22:18:10 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 2543579s — no human required._
