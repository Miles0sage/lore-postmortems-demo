# Postmortem — auth_error

**Cluster:** `ext_f09f7e35`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-21 23:05:35 UTC |
| Recovery confirmed | 2026-01-28 07:32:32 UTC |
| Time to recovery | **548817s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: OpenRouter Claude 3.5 Sonnet - 401 **Error Details**  Model: OpenRouter Claude 3.5 Sonnet Provider: openrouter St…`  

**Error:**
```
**Error Details**  Model: OpenRouter Claude 3.5 Sonnet Provider: openrouter Status Code: 401  **Error Output** ``` 401 User not found. ```  **Additional Context** Please add any additional context abo
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 548817s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-21 23:05:35 UTC |
| Last seen | 2026-01-28 07:32:32 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 548817s — no human required._
