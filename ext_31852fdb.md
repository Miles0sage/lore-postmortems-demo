# Postmortem — timeout_error

**Cluster:** `ext_31852fdb`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-06 21:58:34 UTC |
| Recovery confirmed | 2026-04-06 21:59:13 UTC |
| Time to recovery | **39s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Feature Request] Add web-to-CLI project context synchronization **Bug Description** I want to sync my projects context …`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/danielhurtado/.local/share/claude/versions/2.1.92 (expected in multi-process scenarios)\n    at im_ (/$bunfs/root/src/entrypoints/cli.js
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 39s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-06 21:58:34 UTC |
| Last seen | 2026-04-06 21:59:13 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 39s — no human required._
