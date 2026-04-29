# Postmortem — compatibility_error

**Cluster:** `ext_d72ed2ec`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-30 17:01:17 UTC |
| Recovery confirmed | 2026-04-02 21:32:57 UTC |
| Time to recovery | **275500s** |

---

## What Broke

**Tool:** `unknown_tool`  
**Input:** `Cline tried to use attempt_completion without value for required parameter 'result'. Retrying... ### Plugin Type  VSCode…`  

**Error:**
```
appears right at the end, when the action of the AI model is implemented, it retries 1 or 2 times then it succeeds. I noticed that this happens often when for Planning mode i use another model (not fr
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 275500s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-30 17:01:17 UTC |
| Last seen | 2026-04-02 21:32:57 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: compatibility_error in unknown_tool is recoverable via unknown in 275500s — no human required._
