# Postmortem — auth_error

**Cluster:** `ext_a6fa0595`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-25 00:07:30 UTC |
| Recovery confirmed | 2026-04-28 09:51:37 UTC |
| Time to recovery | **294247s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `OAuth auto-refresh fails in non-interactive (subprocess) mode → 401 after token expiry # Bug Report: Claude CLI OAuth au…`  

**Error:**
```
"Failed to authenticate. API Error: 401
```

---

## What Worked

**Tool:** `bash`  
**Input:** `discovered: directly POSTing to `https://platform.claude.com/v1/oauth/token` with the `refresh_token` works perfectly an…`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 294247s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-25 00:07:30 UTC |
| Last seen | 2026-04-28 09:51:37 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 294247s — no human required._
