# Postmortem — auth_error

**Cluster:** `ext_15ecec01`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-26 18:43:14 UTC |
| Recovery confirmed | 2026-02-26 23:12:49 UTC |
| Time to recovery | **16175s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `OCA auth: stale tokens not cleared on refresh failure, causing repeated sign-in errors ## Summary  Oracle Code Assist (O…`  

**Error:**
```
ERROR oca sign-in error
```

---

## What Worked

**Tool:** `bash`  
**Input:** `Quit VS Code completely, then run:`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 16175s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-26 18:43:14 UTC |
| Last seen | 2026-02-26 23:12:49 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 16175s — no human required._
