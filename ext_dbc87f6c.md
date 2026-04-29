# Postmortem — auth_error

**Cluster:** `ext_dbc87f6c`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-05 09:05:11 UTC |
| Recovery confirmed | 2026-04-08 09:27:25 UTC |
| Time to recovery | **260534s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] RemoteTrigger tool returns 401 in Desktop app while UI can create triggers successfully ### Preflight Checklist  -…`  

**Error:**
```
{"type":"error","error":{"type":"authentication_error","message":"Authentication failed"},"request_id":"req_011CZkLNQEWbJA8vDdPEos5o"}
```

---

## What Worked

**Tool:** `bash`  
**Input:** `by deleting Keychain credentials and re-authenticating`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 260534s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-05 09:05:11 UTC |
| Last seen | 2026-04-08 09:27:25 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 260534s — no human required._
