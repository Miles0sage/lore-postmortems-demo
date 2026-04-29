# Postmortem — timeout_error

**Cluster:** `ext_bd7a6d34`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-20 19:24:07 UTC |
| Recovery confirmed | 2026-04-24 09:39:10 UTC |
| Time to recovery | **310503s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Cowork workspace VM connection timeout on ARM Windows ### Preflight Checklist  - [x] I have searched [existing issues](h…`  

**Error:**
```
Failed to start Claude's workspace
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 310503s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-20 19:24:07 UTC |
| Last seen | 2026-04-24 09:39:10 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 310503s — no human required._
