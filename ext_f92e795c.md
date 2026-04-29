# Postmortem — auth_error

**Cluster:** `ext_f92e795c`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-22 17:59:46 UTC |
| Recovery confirmed | 2026-03-23 18:42:39 UTC |
| Time to recovery | **88973s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Groq Llama 3.3 - 401 **Error Details**  Model: Groq Llama 3.3 Provider: groq Status Code: 401  **Error Output** `…`  

**Error:**
```
**Error Details**  Model: Groq Llama 3.3 Provider: groq Status Code: 401  **Error Output** ``` 401 Invalid API Key ```  **Additional Context** Please add any additional context about the error here
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 88973s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-22 17:59:46 UTC |
| Last seen | 2026-03-23 18:42:39 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 88973s — no human required._
