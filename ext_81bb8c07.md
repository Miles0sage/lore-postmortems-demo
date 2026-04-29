# Postmortem — auth_error

**Cluster:** `ext_81bb8c07`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-08 07:40:43 UTC |
| Recovery confirmed | 2026-04-08 21:54:27 UTC |
| Time to recovery | **51224s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] v2.1.96: Claude Code GitHub Action fails with AWS authentication ### Preflight Checklist  - [x] I have searched [e…`  

**Error:**
```
Error: Action failed with error: SDK execution error: Error: Claude Code returned an error result: Failed to authenticate. API Error: 403 Authorization header requires 'Credential' parameter. Authoriz
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 51224s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-08 07:40:43 UTC |
| Last seen | 2026-04-08 21:54:27 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 51224s — no human required._
