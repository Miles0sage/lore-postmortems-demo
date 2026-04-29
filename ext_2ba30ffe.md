# Postmortem — auth_error

**Cluster:** `ext_2ba30ffe`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-28 08:46:31 UTC |
| Recovery confirmed | 2026-04-28 18:03:45 UTC |
| Time to recovery | **33434s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] v2.1.121: CLAUDE_CODE_DISABLE_EXPERIMENTAL_BETAS=1 + Opus 4.7 causes 401 "OAuth authentication is currently not su…`  

**Error:**
```
API Error (attempt N/11): 401 {"type":"error","error":{"type":"authentication_error","message":"OAuth authentication is currently not supported."}}
```

---

## What Worked

**Tool:** `bash`  
**Input:** ``ANTHROPIC_BETAS` environment variable being silently ignored when using Haiku models`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 33434s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-28 08:46:31 UTC |
| Last seen | 2026-04-28 18:03:45 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 33434s — no human required._
