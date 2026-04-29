# Postmortem — auth_error

**Cluster:** `ext_6ca2edd6`  
**Severity:** LOW (n_observations: 3)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-16 18:45:47 UTC |
| Recovery confirmed | 2026-03-26 00:44:48 UTC |
| Time to recovery | **3218341s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Moonshot Chat - 401 **Error Details**  Model: Moonshot Chat Provider: moonshot Status Code: 401  **Error Output**…`  

**Error:**
```
**Error Details**  Model: Moonshot Chat Provider: moonshot Status Code: 401  **Error Output** ``` 401 Invalid Authentication ```  **Additional Context** Please add any additional context about the err
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

This failure pattern has been observed **3 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 3218341s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-16 18:45:47 UTC |
| Last seen | 2026-03-26 00:44:48 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 3218341s — no human required._
