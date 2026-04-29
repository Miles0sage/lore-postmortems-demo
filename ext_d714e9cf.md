# Postmortem — auth_error

**Cluster:** `ext_d714e9cf`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-08 18:50:39 UTC |
| Recovery confirmed | 2026-03-23 20:46:28 UTC |
| Time to recovery | **3722149s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: DeepSeek Coder (1) - 401 **Error Details**  Model: DeepSeek Coder (1) Provider: deepseek Status Code: 401  **Erro…`  

**Error:**
```
**Error Details**  Model: DeepSeek Coder (1) Provider: deepseek Status Code: 401  **Error Output** ``` 401 Authentication Fails, Your api key: ****json is invalid ```  **Additional Context** Please ad
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3722149s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-08 18:50:39 UTC |
| Last seen | 2026-03-23 20:46:28 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 3722149s — no human required._
