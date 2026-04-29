# Postmortem — auth_error

**Cluster:** `ext_7df3fc84`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-13 23:07:31 UTC |
| Recovery confirmed | 2026-04-13 23:08:56 UTC |
| Time to recovery | **85s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Telegram plugin: frequent HTTP 401 errors mid-session ## Description  The Telegram plugin (v0.0.5) frequently returns HT…`  

**Error:**
```
HTTP 401: authentication_error: Invalid authentication credentials
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 85s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-13 23:07:31 UTC |
| Last seen | 2026-04-13 23:08:56 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 85s — no human required._
