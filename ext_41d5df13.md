# Postmortem — timeout_error

**Cluster:** `ext_41d5df13`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-10 02:48:33 UTC |
| Recovery confirmed | 2026-04-13 09:40:25 UTC |
| Time to recovery | **283912s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] can't run cowork in Snapdragon X ### Preflight Checklist  - [x] I have searched [existing issues](https://github.c…`  

**Error:**
```
VM connection timeout after 60 seconds
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 283912s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-10 02:48:33 UTC |
| Last seen | 2026-04-13 09:40:25 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 283912s — no human required._
