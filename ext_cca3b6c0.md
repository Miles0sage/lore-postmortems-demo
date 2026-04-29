# Postmortem — auth_error

**Cluster:** `ext_cca3b6c0`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-26 13:37:45 UTC |
| Recovery confirmed | 2026-04-26 22:18:09 UTC |
| Time to recovery | **2709624s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] 403 on Claude Desktop Cowork (Win64) ### Preflight Checklist  - [x] I have searched [existing issues](https://gith…`  

**Error:**
```
Messages/Logs
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2709624s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-26 13:37:45 UTC |
| Last seen | 2026-04-26 22:18:09 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 2709624s — no human required._
