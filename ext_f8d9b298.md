# Postmortem — auth_error

**Cluster:** `ext_f8d9b298`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-08 15:32:13 UTC |
| Recovery confirmed | 2026-03-19 20:54:07 UTC |
| Time to recovery | **3388914s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: kimi - 401 **Error Details**  Model: kimi Provider: openai Status Code: 401  **Error Output** ``` 401 Incorrect A…`  

**Error:**
```
**Error Details**  Model: kimi Provider: openai Status Code: 401  **Error Output** ``` 401 Incorrect API key provided: sk-LEMBA***************************************b5Zh. You can find your API key at
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3388914s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-08 15:32:13 UTC |
| Last seen | 2026-03-19 20:54:07 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 3388914s — no human required._
