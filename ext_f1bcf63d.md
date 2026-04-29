# Postmortem — timeout_error

**Cluster:** `ext_f1bcf63d`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-22 18:38:46 UTC |
| Recovery confirmed | 2026-04-26 09:24:18 UTC |
| Time to recovery | **312332s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `You've hit your limit · resets 2:30am (Asia/Calcutta) **Bug Description** how did you used all of my token in 1 doc , wh…`  

**Error:**
```
[{"error":"Error: Failed to fetch version from https://storage.googleapis.com/claude-code-dist-86c565f3-f756-42ad-8dfa-d59b1c096819/claude-code-releases/latest: ECONNREFUSED\n    at up1 (/$bunfs/root/
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 312332s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-22 18:38:46 UTC |
| Last seen | 2026-04-26 09:24:18 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 312332s — no human required._
