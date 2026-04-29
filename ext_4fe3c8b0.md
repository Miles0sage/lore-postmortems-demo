# Postmortem — auth_error

**Cluster:** `ext_4fe3c8b0`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-20 05:06:25 UTC |
| Recovery confirmed | 2026-04-18 04:16:45 UTC |
| Time to recovery | **2502620s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Remote control bridge should auto-refresh OAuth token before expiry ## Summary  The remote control bridge silently dies …`  

**Error:**
```
to the connected client rather than silently continuing to poll
```

---

## What Worked

**Tool:** `read_file`  
**Input:** `- Proactively refresh the OAuth token before TTL expiry (e.g., at 80% of TTL)`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2502620s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-20 05:06:25 UTC |
| Last seen | 2026-04-18 04:16:45 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via read_file in 2502620s — no human required._
