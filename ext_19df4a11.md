# Postmortem — compatibility_error

**Cluster:** `ext_19df4a11`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-27 15:07:43 UTC |
| Recovery confirmed | 2026-01-29 19:42:10 UTC |
| Time to recovery | **5459667s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `No free port found in range 26040..26340 ### Plugin Type  JetBrains Plugin  ### Cline Version  1.1.6  ### What happened?…`  

**Error:**
```
appeared on IDE launch: Checked on Idea, Android Studio
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5459667s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-27 15:07:43 UTC |
| Last seen | 2026-01-29 19:42:10 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: compatibility_error in bash is recoverable via unknown in 5459667s — no human required._
