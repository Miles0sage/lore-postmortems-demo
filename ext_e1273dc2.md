# Postmortem — auth_error

**Cluster:** `ext_e1273dc2`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-18 14:54:30 UTC |
| Recovery confirmed | 2026-04-25 11:33:30 UTC |
| Time to recovery | **592740s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `SDK OAuth refresh silently skipped when expiresAt is outside the 5-minute window (Gate 2 ignores force=true) ## Summary …`  

**Error:**
```
mentioning the token at all.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 592740s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-18 14:54:30 UTC |
| Last seen | 2026-04-25 11:33:30 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 592740s — no human required._
