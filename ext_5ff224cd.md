# Postmortem — auth_error

**Cluster:** `ext_5ff224cd`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-20 13:07:14 UTC |
| Recovery confirmed | 2026-03-26 00:45:18 UTC |
| Time to recovery | **5571484s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: Qwen/Qwen3-Coder-30B-A3B-Instruct-FP8 - 401 **Error Details**  Model: Qwen/Qwen3-Coder-30B-A3B-Instruct-FP8 Provi…`  

**Error:**
```
**Error Details**  Model: Qwen/Qwen3-Coder-30B-A3B-Instruct-FP8 Provider: openai Status Code: 401  **Error Output** ``` 401 status code (no body) ```  **Additional Context** Please add any additional
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5571484s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-20 13:07:14 UTC |
| Last seen | 2026-03-26 00:45:18 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 5571484s — no human required._
