# Postmortem — timeout_error

**Cluster:** `ext_960c0afa`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-03 17:07:53 UTC |
| Recovery confirmed | 2026-04-07 09:30:50 UTC |
| Time to recovery | **318177s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Claude Code process hangs and becomes unresponsive requiring terminal restart **Bug Description** three times toda…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/jasonpurdy/.local/share/claude/versions/2.1.85 (expected in multi-process scenarios)\n    at vp_ (/$bunfs/root/src/entrypoints/cli.js:27
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 318177s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-03 17:07:53 UTC |
| Last seen | 2026-04-07 09:30:50 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 318177s — no human required._
