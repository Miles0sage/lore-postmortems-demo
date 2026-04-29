# Postmortem — timeout_error

**Cluster:** `ext_04b1c4a6`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-23 17:02:42 UTC |
| Recovery confirmed | 2026-04-21 10:37:21 UTC |
| Time to recovery | **2482479s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug Report: Unspecified error or performance issue **Bug Description** What the fuck, guys? Why is it so extremely fuck…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/eb/.local/share/claude/versions/2.1.78 (expected in multi-process scenarios)\n    at gVT (/$bunfs/root/src/entrypoints/cli.js:2648:2174)
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2482479s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-23 17:02:42 UTC |
| Last seen | 2026-04-21 10:37:21 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 2482479s — no human required._
