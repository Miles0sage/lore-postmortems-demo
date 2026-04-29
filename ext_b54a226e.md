# Postmortem — auth_error

**Cluster:** `ext_b54a226e`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-17 07:47:42 UTC |
| Recovery confirmed | 2026-04-20 09:38:49 UTC |
| Time to recovery | **265867s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Feature Request] Allow editing Claude settings in auto mode when explicitly requested **Bug Description** it should all…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/david/.local/share/claude/versions/2.1.112 (expected in multi-process scenarios)\n    at Od_ (/$bunfs/root/src/entrypoints/cli.js:2748:2
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 265867s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-17 07:47:42 UTC |
| Last seen | 2026-04-20 09:38:49 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 265867s — no human required._
