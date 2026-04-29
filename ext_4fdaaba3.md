# Postmortem — unhandled_exception

**Cluster:** `ext_4fdaaba3`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-18 10:14:58 UTC |
| Recovery confirmed | 2026-03-25 02:15:40 UTC |
| Time to recovery | **2995242s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Claude 4.5 Opus - Unknown error **Error Details**  Model: Claude 4.5 Opus Provider: anthropic Status Code: N/A  *…`  

**Error:**
```
request to https://api.anthropic.com/v1/messages failed, reason:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2995242s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-18 10:14:58 UTC |
| Last seen | 2026-03-25 02:15:40 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: unhandled_exception in api_call is recoverable via unknown in 2995242s — no human required._
