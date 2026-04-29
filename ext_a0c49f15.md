# Postmortem — unhandled_exception

**Cluster:** `ext_a0c49f15`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-24 05:42:56 UTC |
| Recovery confirmed | 2026-03-23 21:10:57 UTC |
| Time to recovery | **5066881s** |

---

## What Broke

**Tool:** `unknown_tool`  
**Input:** `Error: Claude 4 Sonnet - 502 **Error Details**  Model: Claude 4 Sonnet Provider: anthropic Status Code: 502  **Error Out…`  

**Error:**
```
<title>Error</title>
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5066881s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-24 05:42:56 UTC |
| Last seen | 2026-03-23 21:10:57 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: unhandled_exception in unknown_tool is recoverable via unknown in 5066881s — no human required._
