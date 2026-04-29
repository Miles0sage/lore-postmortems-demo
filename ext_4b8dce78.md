# Postmortem — auth_error

**Cluster:** `ext_4b8dce78`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-30 08:07:38 UTC |
| Recovery confirmed | 2026-04-02 09:24:42 UTC |
| Time to recovery | **263824s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `setup-token generates invalid bearer token (401 Invalid bearer token) ## Bug Description  `claude setup-token` generates…`  

**Error:**
```
Failed to authenticate. API Error: 401
```

---

## What Worked

**Tool:** `bash`  
**Input:** `Use `claude auth login` (interactive) instead of `setup-token`. This produces 8-12h tokens that work, but requires perio…`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 263824s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-30 08:07:38 UTC |
| Last seen | 2026-04-02 09:24:42 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 263824s — no human required._
