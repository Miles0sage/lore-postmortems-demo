# Postmortem — dependency_error

**Cluster:** `ext_bf6ba23f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-03-30 09:54:45 UTC |
| Recovery confirmed | 2025-12-22 21:45:10 UTC |
| Time to recovery | **23111425s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Failed to Build by tsc ### What happened?  I tried to build this cline project by below command for development this pro…`  

**Error:**
```
tsconfig.app.json:21:3 - error TS5023: Unknown compiler option 'noUncheckedSideEffectImports'.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 23111425s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-03-30 09:54:45 UTC |
| Last seen | 2025-12-22 21:45:10 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via unknown in 23111425s — no human required._
