# Postmortem — auth_error

**Cluster:** `ext_d8c6a5ed`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-30 02:47:29 UTC |
| Recovery confirmed | 2026-03-26 00:03:03 UTC |
| Time to recovery | **4742134s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: kimi-k2.5:cloud - 401 **Error Details**  Model: kimi-k2.5:cloud Provider: ollama Status Code: 401  **Error Output…`  

**Error:**
```
**Error Details**  Model: kimi-k2.5:cloud Provider: ollama Status Code: 401  **Error Output** ``` "unauthorized" ```  **Additional Context** Please add any additional context about the error here
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

This failure pattern has been observed **2 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4742134s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-30 02:47:29 UTC |
| Last seen | 2026-03-26 00:03:03 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 4742134s — no human required._
