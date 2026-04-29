# Postmortem — auth_error

**Cluster:** `ext_a846b67e`  
**Severity:** LOW (n_observations: 2)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-14 07:07:08 UTC |
| Recovery confirmed | 2026-03-19 22:28:02 UTC |
| Time to recovery | **487254s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: gpt-oss:120b-cloud - 401 **Error Details**  Model: gpt-oss:120b-cloud Provider: ollama Status Code: 401  **Error …`  

**Error:**
```
**Error Details**  Model: gpt-oss:120b-cloud Provider: ollama Status Code: 401  **Error Output** ``` "unauthorized" ```  **Additional Context** Please add any additional context about the error here
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 487254s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-14 07:07:08 UTC |
| Last seen | 2026-03-19 22:28:02 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 487254s — no human required._
