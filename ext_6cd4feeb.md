# Postmortem — timeout_error

**Cluster:** `ext_6cd4feeb`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-18 14:40:53 UTC |
| Recovery confirmed | 2026-04-22 09:38:49 UTC |
| Time to recovery | **327476s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Claude Code CLI Performance: Slow Execution Speed **Bug Description** lo noto muy lento.  **Environment Info** - P…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/oscarcortijo/.local/share/claude/versions/2.1.114 (expected in multi-process scenarios)\n    at sd_ (/$bunfs/root/src/entrypoints/cli.js
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 327476s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-18 14:40:53 UTC |
| Last seen | 2026-04-22 09:38:49 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 327476s — no human required._
