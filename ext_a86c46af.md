# Postmortem — compatibility_error

**Cluster:** `ext_a86c46af`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-02 06:38:33 UTC |
| Recovery confirmed | 2025-12-16 20:29:09 UTC |
| Time to recovery | **25019436s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `API Request Failed - Azure o3-mini ### What happened?  Cline 3.5.0 > API Provider ? OpenAI Compatible.   400 Unsupported…`  

**Error:**
```
### What happened?  Cline 3.5.0 > API Provider ? OpenAI Compatible.   400 Unsupported parameter: 'temperature' is not supported with this model.    ### Steps to reproduce  1. 2. 3.   ### Relevant API
```

---

## What Worked

**Tool:** `bash`  
**Input:** `this issue, but it seems to still persist.`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 25019436s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-02 06:38:33 UTC |
| Last seen | 2025-12-16 20:29:09 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: compatibility_error in bash is recoverable via bash in 25019436s — no human required._
