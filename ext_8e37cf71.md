# Postmortem — rate_limit_error

**Cluster:** `ext_8e37cf71`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-25 17:11:59 UTC |
| Recovery confirmed | 2026-04-24 22:20:33 UTC |
| Time to recovery | **2610514s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `You've hit your limit · resets 8pm (Europe/Bucharest) **Bug Description** I am on the 20x plan and I am hitting the rate…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/leon/.local/share/claude/versions/2.1.83 (expected in multi-process scenarios)\n    at rRA (/$bunfs/root/src/entrypoints/cli.js:2735:216
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2610514s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-25 17:11:59 UTC |
| Last seen | 2026-04-24 22:20:33 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: rate_limit_error in bash is recoverable via unknown in 2610514s — no human required._
