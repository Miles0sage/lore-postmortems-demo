# Postmortem — auth_error

**Cluster:** `ext_c995c31f`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-28 17:13:56 UTC |
| Recovery confirmed | 2026-03-23 19:45:09 UTC |
| Time to recovery | **1996273s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: Gemini 3 Pro - 401 **Error Details**  Model: Gemini 3 Pro Provider: openai Status Code: 401  **Error Output** ```…`  

**Error:**
```
**Error Details**  Model: Gemini 3 Pro Provider: openai Status Code: 401  **Error Output** ``` 401 You didn't provide an API key. You need to provide your API key in an Authorization header using Bear
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

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1996273s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-28 17:13:56 UTC |
| Last seen | 2026-03-23 19:45:09 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 1996273s — no human required._
