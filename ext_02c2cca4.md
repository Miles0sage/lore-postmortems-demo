# Postmortem — auth_error

**Cluster:** `ext_02c2cca4`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-18 20:11:12 UTC |
| Recovery confirmed | 2026-04-24 22:20:45 UTC |
| Time to recovery | **8302173s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `OAuth token expired immediately after fresh login - cannot use Claude Code (blocking) ### Preflight Checklist  - [x] I h…`  

**Error:**
```
API Error: 401 {"type":"error","error":{"type":"authentication_error","message":"OAuth token has expired. Please obtain a new token or refresh your existing token."},"request_id":"req_011CXFRbLKkrH6cs
```

---

## What Worked

**Tool:** `bash`  
**Input:** `after several hours on Jan 17`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 8302173s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-18 20:11:12 UTC |
| Last seen | 2026-04-24 22:20:45 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 8302173s — no human required._
