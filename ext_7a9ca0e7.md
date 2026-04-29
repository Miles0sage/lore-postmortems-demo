# Postmortem — auth_error

**Cluster:** `ext_7a9ca0e7`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-22 06:57:23 UTC |
| Recovery confirmed | 2026-01-22 21:54:33 UTC |
| Time to recovery | **53830s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: GPT-4.1 - 401 **Error Details**  Model: GPT-4.1 Provider: openai Status Code: 401  **Error Output** ``` 401 Incor…`  

**Error:**
```
**Error Details**  Model: GPT-4.1 Provider: openai Status Code: 401  **Error Output** ``` 401 Incorrect API key provided: 5hcxvSQt**********************************************************************
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 53830s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-22 06:57:23 UTC |
| Last seen | 2026-01-22 21:54:33 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 53830s — no human required._
