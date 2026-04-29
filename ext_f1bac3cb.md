# Postmortem — timeout_error

**Cluster:** `ext_f1bac3cb`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-06 18:47:18 UTC |
| Recovery confirmed | 2026-04-13 22:21:53 UTC |
| Time to recovery | **617675s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug Report] Unable to process request - missing bug report details **Bug Description**   **Environment Info** - Platfor…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/douglasl/.local/share/claude/versions/2.1.92 (expected in multi-process scenarios)\n    at im_ (/$bunfs/root/src/entrypoints/cli.js:1884
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 617675s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-06 18:47:18 UTC |
| Last seen | 2026-04-13 22:21:53 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 617675s — no human required._
