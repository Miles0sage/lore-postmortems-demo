# Postmortem — auth_error

**Cluster:** `ext_a92fc120`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-17 15:21:10 UTC |
| Recovery confirmed | 2026-03-26 00:44:33 UTC |
| Time to recovery | **725003s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: Kimi API - 401 **Error Details**  Model: Kimi API Provider: openai Status Code: 401  **Error Output** ``` 401 Inv…`  

**Error:**
```
**Error Details**  Model: Kimi API Provider: openai Status Code: 401  **Error Output** ``` 401 Invalid Authentication ```  **Additional Context** Please add any additional context about the error here
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 725003s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-17 15:21:10 UTC |
| Last seen | 2026-03-26 00:44:33 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 725003s — no human required._
