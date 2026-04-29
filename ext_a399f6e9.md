# Postmortem — resource_not_found

**Cluster:** `ext_a399f6e9`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-02-10 17:52:10 UTC |
| Recovery confirmed | 2025-08-01 17:12:17 UTC |
| Time to recovery | **14858407s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Add support for Windows time zone name format ## Bug Description When using Windows system time zone name "中国标准时间", the …`  

**Error:**
```
zoneinfo._common.ZoneInfoNotFoundError: 'No time zone found with key 中国标准时间'
```

---

## What Worked

**Tool:** `api_call`  
**Input:** `Add a mapping from Windows time zone names to IANA time zone names. For example:`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 14858407s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-02-10 17:52:10 UTC |
| Last seen | 2025-08-01 17:12:17 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in api_call is recoverable via api_call in 14858407s — no human required._
