# Postmortem — auth_error

**Cluster:** `ext_a512a8a8`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-10-17 06:26:52 UTC |
| Recovery confirmed | 2025-12-18 20:38:54 UTC |
| Time to recovery | **5407922s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Cline CLI auth doesnot works in Firebase Studio Project IDX Workspaces ### Plugin Type  CLI  ### Cline Version   v3.33.1…`  

**Error:**
```
Authentication failed or timed out.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 5407922s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-10-17 06:26:52 UTC |
| Last seen | 2025-12-18 20:38:54 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 5407922s — no human required._
