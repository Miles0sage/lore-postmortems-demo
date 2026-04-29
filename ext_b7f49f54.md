# Postmortem — unhandled_exception

**Cluster:** `ext_b7f49f54`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-02 10:19:22 UTC |
| Recovery confirmed | 2026-03-23 20:54:53 UTC |
| Time to recovery | **4271731s** |

---

## What Broke

**Tool:** `unknown_tool`  
**Input:** `Error: Claude Sonnet 4.5 - 504 **Error Details**  Model: Claude Sonnet 4.5 Provider: continue-proxy Status Code: 504  **…`  

**Error:**
```
**Error Details**  Model: Claude Sonnet 4.5 Provider: continue-proxy Status Code: 504  **Error Output** ``` <html> <head><title>504 Gateway Time-out</title></head> <body> <center><h1>504 Gateway Ti
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 4271731s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-02 10:19:22 UTC |
| Last seen | 2026-03-23 20:54:53 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: unhandled_exception in unknown_tool is recoverable via unknown in 4271731s — no human required._
