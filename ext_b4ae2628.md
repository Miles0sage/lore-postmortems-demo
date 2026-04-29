# Postmortem — auth_error

**Cluster:** `ext_b4ae2628`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-21 22:55:55 UTC |
| Recovery confirmed | 2026-03-26 00:02:54 UTC |
| Time to recovery | **5447219s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: OpenRouter Claude Sonnet - 401 **Error Details**  Model: OpenRouter Claude Sonnet Provider: openrouter Status Cod…`  

**Error:**
```
**Error Details**  Model: OpenRouter Claude Sonnet Provider: openrouter Status Code: 401  **Error Output** ``` 401 User not found. ```  **Additional Context** Please add any additional context about t
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5447219s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-21 22:55:55 UTC |
| Last seen | 2026-03-26 00:02:54 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 5447219s — no human required._
