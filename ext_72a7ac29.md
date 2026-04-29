# Postmortem — timeout_error

**Cluster:** `ext_72a7ac29`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-02 09:54:41 UTC |
| Recovery confirmed | 2026-04-09 10:31:34 UTC |
| Time to recovery | **607013s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Claude Code agent exhibits inconsistent behavior and memory loss during sessions **Bug Description** "Today claude…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/philippvolgger/.local/share/claude/versions/2.1.90 (expected in multi-process scenarios)\n    at Cu_ (/$bunfs/root/src/entrypoints/cli.j
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 607013s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-02 09:54:41 UTC |
| Last seen | 2026-04-09 10:31:34 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 607013s — no human required._
