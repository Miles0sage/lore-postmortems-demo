# Postmortem — timeout_error

**Cluster:** `ext_b9362a7d`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-27 10:51:01 UTC |
| Recovery confirmed | 2026-03-03 08:29:20 UTC |
| Time to recovery | **337099s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Checkpoints feature corrupts git repo in large monorepo: infinite nested .git in node_modules, permanently renames .git …`  

**Error:**
```
ERROR CheckpointTracker failed to disable nested git repo node_modules/claude-dev/node_modules/claude-dev/.git:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 337099s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-27 10:51:01 UTC |
| Last seen | 2026-03-03 08:29:20 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 337099s — no human required._
