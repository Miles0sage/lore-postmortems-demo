# Postmortem — auth_error

**Cluster:** `ext_db38f5eb`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-07 10:52:40 UTC |
| Recovery confirmed | 2026-03-25 02:53:08 UTC |
| Time to recovery | **3945628s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: Trinity Large - 401 **Error Details**  Model: Trinity Large Provider: openai Status Code: 401  **Error Output** `…`  

**Error:**
```
**Error Details**  Model: Trinity Large Provider: openai Status Code: 401  **Error Output** ``` 401 You didn't provide an API key. You need to provide your API key in an Authorization header using Bea
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3945628s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-07 10:52:40 UTC |
| Last seen | 2026-03-25 02:53:08 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 3945628s — no human required._
