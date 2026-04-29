# Postmortem — auth_error

**Cluster:** `ext_db13c9a9`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-22 07:34:20 UTC |
| Recovery confirmed | 2026-02-03 07:45:18 UTC |
| Time to recovery | **1037458s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Error: Claude 3.7 Sonnet - 401 **Error Details**  Model: Claude 3.7 Sonnet Provider: anthropic Status Code: 401  **Error…`  

**Error:**
```
{"type":"authentication_error","message":"invalid x-api-key"}
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1037458s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-22 07:34:20 UTC |
| Last seen | 2026-02-03 07:45:18 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 1037458s — no human required._
