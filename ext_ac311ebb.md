# Postmortem — timeout_error

**Cluster:** `ext_ac311ebb`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-06 04:35:17 UTC |
| Recovery confirmed | 2026-04-09 09:31:37 UTC |
| Time to recovery | **276980s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Scroll functionality not working in Ghostyy interface **Bug Description** No able to scroll on Ghostyy  **Environm…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /home/sidhartha/.local/share/claude/versions/2.1.92 (expected in multi-process scenarios)\n    at Qm$ (/$bunfs/root/src/entrypoints/cli.js:1882
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 276980s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-06 04:35:17 UTC |
| Last seen | 2026-04-09 09:31:37 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 276980s — no human required._
