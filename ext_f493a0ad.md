# Postmortem — auth_error

**Cluster:** `ext_f493a0ad`  
**Severity:** LOW (n_observations: 3)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-21 15:29:07 UTC |
| Recovery confirmed | 2026-01-26 22:40:52 UTC |
| Time to recovery | **457905s** |

---

## What Broke

**Tool:** `edit_file`  
**Input:** `Error: Claude Sonnet 4.5 - 401 **Error Details**  Model: Claude Sonnet 4.5 Provider: continue-proxy Status Code: 401  **…`  

**Error:**
```
**Error Details**  Model: Claude Sonnet 4.5 Provider: continue-proxy Status Code: 401  **Error Output** ``` "You have no credits remaining on your Continue account. Please go to https://hub.continue.d
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 457905s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-21 15:29:07 UTC |
| Last seen | 2026-01-26 22:40:52 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in edit_file is recoverable via unknown in 457905s — no human required._
