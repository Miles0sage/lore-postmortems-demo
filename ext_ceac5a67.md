# Postmortem — auth_error

**Cluster:** `ext_ceac5a67`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-30 00:30:07 UTC |
| Recovery confirmed | 2026-01-31 00:19:02 UTC |
| Time to recovery | **85735s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: DeepSeek Coder - 401 **Error Details**  Model: DeepSeek Coder Provider: deepseek Status Code: 401  **Error Output…`  

**Error:**
```
**Error Details**  Model: DeepSeek Coder Provider: deepseek Status Code: 401  **Error Output** ``` 401 Authentication Fails, Your api key: ****null is invalid ```  **Additional Context** Please add an
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 85735s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-30 00:30:07 UTC |
| Last seen | 2026-01-31 00:19:02 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 85735s — no human required._
