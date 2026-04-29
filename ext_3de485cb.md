# Postmortem — auth_error

**Cluster:** `ext_3de485cb`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-17 10:01:09 UTC |
| Recovery confirmed | 2026-04-21 09:40:46 UTC |
| Time to recovery | **344377s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Engineering skills functionality not working **Bug Description** engineering skills is not working for some reason…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/tareqazizhoque7/.local/share/claude/versions/2.1.112 (expected in multi-process scenarios)\n    at Od_ (/$bunfs/root/src/entrypoints/cli
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 344377s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-17 10:01:09 UTC |
| Last seen | 2026-04-21 09:40:46 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 344377s — no human required._
