# Postmortem — auth_error

**Cluster:** `ext_6fba7b02`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-14 22:03:36 UTC |
| Recovery confirmed | 2026-02-16 15:36:36 UTC |
| Time to recovery | **149580s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] `database not available` error persists on Node.js v20 and v24 (macOS arm64) ### Plugin Type  CLI  ### Cline Versi…`  

**Error:**
```
Error: failed to start auth instance: failed to start instance: operation failed to after 12 attempts: instance not found in registry: database not available
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 149580s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-14 22:03:36 UTC |
| Last seen | 2026-02-16 15:36:36 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 149580s — no human required._
