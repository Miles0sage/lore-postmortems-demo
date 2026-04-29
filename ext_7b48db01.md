# Postmortem — schema_validation_error

**Cluster:** `ext_7b48db01`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-04 06:08:07 UTC |
| Recovery confirmed | 2026-02-04 06:53:33 UTC |
| Time to recovery | **2726s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Conversation condensation fails with 400 error when tool history contains regex search patterns with special characters …`  

**Error:**
```
[openrouter] 400 Provider returned error
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2726s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-04 06:08:07 UTC |
| Last seen | 2026-02-04 06:53:33 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: schema_validation_error in read_file is recoverable via unknown in 2726s — no human required._
