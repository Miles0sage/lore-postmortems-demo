# Postmortem — timeout_error

**Cluster:** `ext_d0b3dac7`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-05 23:07:43 UTC |
| Recovery confirmed | 2026-04-20 04:35:24 UTC |
| Time to recovery | **1229261s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Session history repeatedly clearing unexpectedly during active session **Bug Description** i'm not entirely sure w…`  

**Error:**
```
[{"error":"Error: 1P event logging: 5 events failed to export (code=ECONNABORTED, timeout of 10000ms exceeded)\n    at queueFailedEvents (/$bunfs/root/src/entrypoints/cli.js:424:2574)\n    at async do
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1229261s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-05 23:07:43 UTC |
| Last seen | 2026-04-20 04:35:24 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 1229261s — no human required._
