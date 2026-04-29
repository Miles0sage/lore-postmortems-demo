# Postmortem — auth_error

**Cluster:** `ext_00ca8f92`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-24 02:20:37 UTC |
| Recovery confirmed | 2026-04-23 10:37:47 UTC |
| Time to recovery | **2621830s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Test bypassing and incorrect working directory handling during execution **Bug Description** Did a poor job, decid…`  

**Error:**
```
[{"error":"AxiosError: Request failed with status code 403\n    at Uu (/$bunfs/root/src/entrypoints/cli.js:74:1194)\n    at <anonymous> (/$bunfs/root/src/entrypoints/cli.js:79:12762)\n    at emit (nod
```

---

## What Worked

**Tool:** `bash`  
**Input:** `them.  Also span for a long time in the wrong directory`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2621830s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-24 02:20:37 UTC |
| Last seen | 2026-04-23 10:37:47 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 2621830s — no human required._
