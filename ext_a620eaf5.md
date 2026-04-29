# Postmortem — configuration_error

**Cluster:** `ext_a620eaf5`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-04-17 05:00:02 UTC |
| Recovery confirmed | 2025-12-30 21:11:52 UTC |
| Time to recovery | **22263110s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `[Bug Report] Queries Sent After Switching from Act to Plan Mode Are Flagged by Azure “jailbreak” Filter and Return 400 E…`  

**Error:**
```
API Request Failed
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 22263110s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-04-17 05:00:02 UTC |
| Last seen | 2025-12-30 21:11:52 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: configuration_error in read_file is recoverable via unknown in 22263110s — no human required._
