# Postmortem — configuration_error

**Cluster:** `ext_3ca805b1`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-06-06 08:29:42 UTC |
| Recovery confirmed | 2025-12-30 21:23:21 UTC |
| Time to recovery | **17931219s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `How to set a custom model id for the Anthropic API My Claude model comes from a third-party service provider, but my mod…`  

**Error:**
```
My Claude model comes from a third-party service provider, but my model ID is not in the options list in the settings. I want to set a custom model ID for the Anthropic API. How can I achieve this?  !
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 17931219s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-06-06 08:29:42 UTC |
| Last seen | 2025-12-30 21:23:21 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: configuration_error in api_call is recoverable via unknown in 17931219s — no human required._
