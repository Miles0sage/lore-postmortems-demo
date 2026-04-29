# Postmortem — auth_error

**Cluster:** `ext_a95bb60b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-08 12:59:24 UTC |
| Recovery confirmed | 2026-03-26 00:02:59 UTC |
| Time to recovery | **1508615s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: qwen3-next-80b-a3b-instruct:free - 401 **Error Details**  Model: qwen3-next-80b-a3b-instruct:free Provider: openr…`  

**Error:**
```
**Error Details**  Model: qwen3-next-80b-a3b-instruct:free Provider: openrouter Status Code: 401  **Error Output** ``` 401 User not found. ```  **Additional Context** Please add any additional context
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1508615s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-08 12:59:24 UTC |
| Last seen | 2026-03-26 00:02:59 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 1508615s — no human required._
