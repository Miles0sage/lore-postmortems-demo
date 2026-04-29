# Postmortem — auth_error

**Cluster:** `ext_a42e3d4c`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-05 16:54:39 UTC |
| Recovery confirmed | 2026-03-26 00:44:45 UTC |
| Time to recovery | **1756206s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: GPT-OSS 20B Cloud - 401 **Error Details**  Model: GPT-OSS 20B Cloud Provider: ollama Status Code: 401  **Error Ou…`  

**Error:**
```
**Error Details**  Model: GPT-OSS 20B Cloud Provider: ollama Status Code: 401  **Error Output** ``` unauthorized  ```  **Additional Context** Please add any additional context about the error here
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1756206s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-05 16:54:39 UTC |
| Last seen | 2026-03-26 00:44:45 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 1756206s — no human required._
