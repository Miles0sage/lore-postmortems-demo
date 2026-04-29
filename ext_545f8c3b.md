# Postmortem — unhandled_exception

**Cluster:** `ext_545f8c3b`  
**Severity:** LOW (n_observations: 3)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-23 01:58:58 UTC |
| Recovery confirmed | 2026-03-25 02:51:47 UTC |
| Time to recovery | **5273569s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Gemini 2.5 Pro - Unknown error **Error Details**  Model: Gemini 2.5 Pro Provider: gemini Status Code: N/A  **Erro…`  

**Error:**
```
exception TypeError: fetch failed sending request
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5273569s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-23 01:58:58 UTC |
| Last seen | 2026-03-25 02:51:47 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: unhandled_exception in api_call is recoverable via unknown in 5273569s — no human required._
