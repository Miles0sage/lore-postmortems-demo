# Postmortem — auth_error

**Cluster:** `ext_0685d0bb`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-25 07:37:18 UTC |
| Recovery confirmed | 2026-03-25 07:37:23 UTC |
| Time to recovery | **5s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: DeepSeek Chat - 401 **Error Details**  Model: DeepSeek Chat Provider: deepseek Status Code: 401  **Error Output**…`  

**Error:**
```
**Error Details**  Model: DeepSeek Chat Provider: deepseek Status Code: 401  **Error Output** ``` 401 Authentication Fails, Your api key: ****fcc2 is invalid ```  **Additional Context** Please add any
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-25 07:37:18 UTC |
| Last seen | 2026-03-25 07:37:23 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 5s — no human required._
