# Postmortem — unhandled_exception

**Cluster:** `ext_d2a677b7`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-04 14:30:48 UTC |
| Recovery confirmed | 2026-03-25 02:51:54 UTC |
| Time to recovery | **4191666s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Gemini 2.5 Flash - Unknown error **Error Details**  Model: Gemini 2.5 Flash Provider: gemini Status Code: N/A  **…`  

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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4191666s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-04 14:30:48 UTC |
| Last seen | 2026-03-25 02:51:54 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: unhandled_exception in api_call is recoverable via unknown in 4191666s — no human required._
