# Postmortem — auth_error

**Cluster:** `ext_ffc8d0b2`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-23 15:42:57 UTC |
| Recovery confirmed | 2026-04-27 09:53:21 UTC |
| Time to recovery | **324624s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Auto mode classifier blocks PR merge operations **Bug Description** explicitly said to merge the PR i was working …`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /home/jperna7254/.local/share/claude/versions/2.1.116 (expected in multi-process scenarios)\n    at Ol$ (/$bunfs/root/src/entrypoints/cli.js:27
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 324624s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-23 15:42:57 UTC |
| Last seen | 2026-04-27 09:53:21 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 324624s — no human required._
