# Postmortem — auth_error

**Cluster:** `ext_72ead4ee`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-27 23:23:15 UTC |
| Recovery confirmed | 2026-03-23 19:44:14 UTC |
| Time to recovery | **4738859s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Claude 4 Sonnet - 403 **Error Details**  Model: Claude 4 Sonnet Provider: anthropic Status Code: 403  **Error Out…`  

**Error:**
```
**Error Details**  Model: Claude 4 Sonnet Provider: anthropic Status Code: 403  **Error Output** ``` {"type":"forbidden","message":"Request not allowed"} ```  **Additional Context** Please add any add
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4738859s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-27 23:23:15 UTC |
| Last seen | 2026-03-23 19:44:14 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in api_call is recoverable via unknown in 4738859s — no human required._
