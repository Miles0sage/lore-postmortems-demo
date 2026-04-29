# Postmortem — unhandled_exception

**Cluster:** `ext_f2107ab3`  
**Severity:** MED (n_observations: 7)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-22 11:36:53 UTC |
| Recovery confirmed | 2026-02-22 11:38:11 UTC |
| Time to recovery | **78s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Error: Gemini 2.0 Flash - Unknown error **Error Details**  Model: Gemini 2.0 Flash Provider: gemini Status Code: N/A  **…`  

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

This failure pattern has been observed **7 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 78s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-22 11:36:53 UTC |
| Last seen | 2026-02-22 11:38:11 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: unhandled_exception in api_call is recoverable via unknown in 78s — no human required._
