# Postmortem — resource_not_found

**Cluster:** `ext_192ef4a9`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-05 04:58:07 UTC |
| Recovery confirmed | 2026-03-23 19:47:34 UTC |
| Time to recovery | **4027767s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Claude 4.5 Sonnet - Unknown error **Error Details**  Model: Claude 4.5 Sonnet Provider: anthropic Status Code: N/…`  

**Error:**
```
request to https://api-epic.ir-gateway.abbvienet.com/iliad/anthropic/v1/messages failed, reason: getaddrinfo ENOTFOUND api-epic.ir-gateway.abbvienet.com
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4027767s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-05 04:58:07 UTC |
| Last seen | 2026-03-23 19:47:34 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in api_call is recoverable via unknown in 4027767s — no human required._
