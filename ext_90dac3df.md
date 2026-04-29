# Postmortem — timeout_error

**Cluster:** `ext_90dac3df`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-08 15:46:10 UTC |
| Recovery confirmed | 2026-02-08 16:48:07 UTC |
| Time to recovery | **3717s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Gemini 3 Pro - Unknown error **Error Details**  Model: Gemini 3 Pro Provider: gemini Status Code: N/A  **Error Ou…`  

**Error:**
```
exception TypeError: fetch failed sending request
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3717s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-08 15:46:10 UTC |
| Last seen | 2026-02-08 16:48:07 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in api_call is recoverable via unknown in 3717s — no human required._
