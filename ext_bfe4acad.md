# Postmortem — auth_error

**Cluster:** `ext_bfe4acad`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-20 00:17:41 UTC |
| Recovery confirmed | 2026-01-22 21:50:21 UTC |
| Time to recovery | **250360s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: Claude .45 Sonnet - 401 **Error Details**  Model: Claude .45 Sonnet Provider: openai Status Code: 401  **Error Ou…`  

**Error:**
```
**Error Details**  Model: Claude .45 Sonnet Provider: openai Status Code: 401  **Error Output** ``` 401 Incorrect API key provided: sk-or-v1******.39a. You can find your API key at https://platform.op
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 250360s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-20 00:17:41 UTC |
| Last seen | 2026-01-22 21:50:21 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 250360s — no human required._
