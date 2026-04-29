# Postmortem — auth_error

**Cluster:** `ext_e5bd6f4f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-12 13:45:04 UTC |
| Recovery confirmed | 2026-04-12 10:19:34 UTC |
| Time to recovery | **2666070s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] Cloud environment allowlist missing cache.ruby-lang.org — rbenv install fails with 403 ### Preflight Checklist  - …`  

**Error:**
```
curl: (22) The requested URL returned error: 403
```

---

## What Worked

**Tool:** `bash`  
**Input:** `Add `cache.ruby-lang.org` to the default allowed domains under "Package Managers - Ruby". Alternatively, use a wildcard …`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2666070s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-12 13:45:04 UTC |
| Last seen | 2026-04-12 10:19:34 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 2666070s — no human required._
