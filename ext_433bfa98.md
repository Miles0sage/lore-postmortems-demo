# Postmortem — auth_error

**Cluster:** `ext_433bfa98`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-05 16:05:24 UTC |
| Recovery confirmed | 2026-04-09 09:34:28 UTC |
| Time to recovery | **322144s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `SessionStart hook reports error on /compact with no actionable details ## Summary  When `/compact` triggers a `SessionSt…`  

**Error:**
```
message appears after compaction. No stderr output, no stack trace, no indication of what failed. The hook's JSON output is valid and the process exits cleanly when run manually.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 322144s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-05 16:05:24 UTC |
| Last seen | 2026-04-09 09:34:28 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 322144s — no human required._
