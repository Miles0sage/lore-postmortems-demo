# Postmortem — network_error

**Cluster:** `ext_09eebab7`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-25 01:26:48 UTC |
| Recovery confirmed | 2026-03-28 09:14:28 UTC |
| Time to recovery | **287260s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Missing command suggestions in terminal after initial message **Bug Description** No more suggestions in the termi…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/macdetheo/.local/share/claude/versions/2.1.81 (expected in multi-process scenarios)\n    at TET (/$bunfs/root/src/entrypoints/cli.js:272
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 287260s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-25 01:26:48 UTC |
| Last seen | 2026-03-28 09:14:28 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 287260s — no human required._
