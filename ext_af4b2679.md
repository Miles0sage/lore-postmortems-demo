# Postmortem — unhandled_exception

**Cluster:** `ext_af4b2679`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-29 07:13:27 UTC |
| Recovery confirmed | 2026-03-25 02:51:51 UTC |
| Time to recovery | **4736304s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: errorexception TypeError: fetch failed sending request **Error Details**  Model: Gemini 3 Pro Provider: gemini St…`  

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

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4736304s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-29 07:13:27 UTC |
| Last seen | 2026-03-25 02:51:51 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: unhandled_exception in api_call is recoverable via unknown in 4736304s — no human required._
