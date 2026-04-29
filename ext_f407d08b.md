# Postmortem — auth_error

**Cluster:** `ext_f407d08b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-07-31 03:36:44 UTC |
| Recovery confirmed | 2026-01-07 19:51:33 UTC |
| Time to recovery | **13882489s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Custom Base URL Gemini Request Fails to Replace x-goog-api-key, Resulting in 401 Invalid Key Error ### What happened?  I…`  

**Error:**
```
### What happened?  In the Gemini model configuration, when using a custom base URL to call Gemini, the x-goog-api-key header did not get replaced with the key value provided by the base URL, causing
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 13882489s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-07-31 03:36:44 UTC |
| Last seen | 2026-01-07 19:51:33 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 13882489s — no human required._
