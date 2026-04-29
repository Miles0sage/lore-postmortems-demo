# Postmortem — auth_error

**Cluster:** `ext_c65241ae`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-03 13:57:19 UTC |
| Recovery confirmed | 2026-03-26 00:03:01 UTC |
| Time to recovery | **4356342s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: <Open Router> - 401 **Error Details**  Model: <Open Router> Provider: openrouter Status Code: 401  **Error Output…`  

**Error:**
```
**Error Details**  Model: <Open Router> Provider: openrouter Status Code: 401  **Error Output** ``` 401 No cookie auth credentials found ```  **Additional Context** Please add any additional context a
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4356342s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-03 13:57:19 UTC |
| Last seen | 2026-03-26 00:03:01 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 4356342s — no human required._
