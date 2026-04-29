# Postmortem — resource_not_found

**Cluster:** `ext_f0e6124d`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-28 13:47:19 UTC |
| Recovery confirmed | 2026-03-23 19:47:08 UTC |
| Time to recovery | **2008789s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Claude Opus 4.6 - Unknown error **Error Details**  Model: Claude Opus 4.6 Provider: anthropic Status Code: N/A  *…`  

**Error:**
```
request to https://api.anthropic.com/v1/messages failed, reason: getaddrinfo ENOTFOUND api.anthropic.com
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2008789s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-28 13:47:19 UTC |
| Last seen | 2026-03-23 19:47:08 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in api_call is recoverable via unknown in 2008789s — no human required._
