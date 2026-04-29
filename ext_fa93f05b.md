# Postmortem — auth_error

**Cluster:** `ext_fa93f05b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-18 03:09:34 UTC |
| Recovery confirmed | 2026-03-21 09:10:45 UTC |
| Time to recovery | **280871s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Git push failing with HTTP 403 error" ### Preflight Checklist  - [x] I have searched [existing issues](https://github.co…`  

**Error:**
```
Description: I'm trying to push a commit to my repository (smagnacca/60-second-ai-quiz) but getting persistent "HTTP 403" errors. The commit is saved locally but won't push to GitHub. This happens eve
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 280871s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-18 03:09:34 UTC |
| Last seen | 2026-03-21 09:10:45 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 280871s — no human required._
