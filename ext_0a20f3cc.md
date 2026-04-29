# Postmortem — compatibility_error

**Cluster:** `ext_0a20f3cc`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-07-18 14:44:47 UTC |
| Recovery confirmed | 2026-03-22 13:05:30 UTC |
| Time to recovery | **21334843s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Failed to use Azure OpenAI o3-pro // Azure OpenAI Responses API Needed. ### What happened?  Using the OpenAI-compatible …`  

**Error:**
```
### What happened?  Using the OpenAI-compatible method, I can't use the o3-pro model, which requires the Responses API. Recently, Azure OpenAI enabled their Responses API:  https://learn.microsoft.com
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 21334843s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-07-18 14:44:47 UTC |
| Last seen | 2026-03-22 13:05:30 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: compatibility_error in bash is recoverable via unknown in 21334843s — no human required._
