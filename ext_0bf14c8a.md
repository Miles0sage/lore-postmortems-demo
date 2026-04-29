# Postmortem — context_overflow

**Cluster:** `ext_0bf14c8a`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-13 15:39:48 UTC |
| Recovery confirmed | 2026-04-17 09:39:28 UTC |
| Time to recovery | **323980s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `API Error: 500 {"type":"error","error":{"type":"api_error",... **Bug Description**  API Error: 500 {"type":"error","erro…`  

**Error:**
```
500 {"type":"error","error":{"type":"api_error","message":"Internal server
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 323980s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-13 15:39:48 UTC |
| Last seen | 2026-04-17 09:39:28 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: context_overflow in bash is recoverable via unknown in 323980s — no human required._
