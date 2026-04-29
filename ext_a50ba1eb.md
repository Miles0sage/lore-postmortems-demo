# Postmortem — auth_error

**Cluster:** `ext_a50ba1eb`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-20 13:16:19 UTC |
| Recovery confirmed | 2026-03-25 02:34:12 UTC |
| Time to recovery | **2812673s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: qwen3.5:397b-cloud - 403 **Error Details**  Model: qwen3.5:397b-cloud Provider: ollama Status Code: 403  **Error …`  

**Error:**
```
**Error Details**  Model: qwen3.5:397b-cloud Provider: ollama Status Code: 403  **Error Output** ``` "" ```  **Additional Context** Please add any additional context about the error here
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2812673s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-20 13:16:19 UTC |
| Last seen | 2026-03-25 02:34:12 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 2812673s — no human required._
