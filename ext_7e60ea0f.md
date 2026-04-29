# Postmortem — auth_error

**Cluster:** `ext_7e60ea0f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-23 17:42:23 UTC |
| Recovery confirmed | 2026-04-27 09:52:47 UTC |
| Time to recovery | **317424s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] Cowork: WebFetch blocked by AllTrails edge protection (403) while Claude.ai web_fetch succeeds on same URLs ### Pr…`  

**Error:**
```
Error responses from this session:
```

---

## What Worked

**Tool:** `bash`  
**Input:** `likely requires updating the fetch fingerprint (user-agent, TLS profile, or IP range) to whatever Claude.ai uses so Clou…`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 317424s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-23 17:42:23 UTC |
| Last seen | 2026-04-27 09:52:47 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 317424s — no human required._
