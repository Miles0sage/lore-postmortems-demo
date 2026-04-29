# Postmortem — auth_error

**Cluster:** `ext_c921b4e6`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-17 10:07:31 UTC |
| Recovery confirmed | 2026-03-20 10:16:00 UTC |
| Time to recovery | **259709s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Partner Registration Form Returns HTTP 403 Akamai WAF Block on Submit **Bug Description** Partner Registration for…`  

**Error:**
```
[{"error":"Error: Request was aborted.\n    at xEA (B:/~BUN/root/src/entrypoints/cli.js:1246:68515)\n    at next (native:1:11)\n    at xK_ (B:/~BUN/root/src/entrypoints/cli.js:6483:6962)\n    at next
```

---

## What Worked

**Tool:** `bash`  
**Input:** `to <input required=\"\" type=\"radio\" name=\"-99f4\" id=\"PICKER-1-37\" lwc-1lsho6rb566=\"\" value=\"Partner_Program\"/…`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 259709s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-17 10:07:31 UTC |
| Last seen | 2026-03-20 10:16:00 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 259709s — no human required._
