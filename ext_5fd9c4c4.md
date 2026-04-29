# Postmortem — auth_error

**Cluster:** `ext_5fd9c4c4`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-22 00:33:24 UTC |
| Recovery confirmed | 2026-01-26 22:50:41 UTC |
| Time to recovery | **425837s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Claude 3.7 Sonnet - 403 **Error Details**  Model: Claude 3.7 Sonnet Provider: anthropic Status Code: 403  **Error…`  

**Error:**
```
**Error Details**  Model: Claude 3.7 Sonnet Provider: anthropic Status Code: 403  **Error Output** ``` {"type":"forbidden","message":"Request not allowed"} ```  **Additional Context** Please add any a
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 425837s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-22 00:33:24 UTC |
| Last seen | 2026-01-26 22:50:41 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 425837s — no human required._
