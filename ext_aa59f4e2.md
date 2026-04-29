# Postmortem — compatibility_error

**Cluster:** `ext_aa59f4e2`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-03 03:27:31 UTC |
| Recovery confirmed | 2026-03-22 13:05:30 UTC |
| Time to recovery | **12044279s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Cline + vscode-lm: All models return 'Model is not supported' error ### Plugin Type  VSCode Extension  ### Cline Version…`  

**Error:**
```
message is:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 12044279s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-03 03:27:31 UTC |
| Last seen | 2026-03-22 13:05:30 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: compatibility_error in api_call is recoverable via unknown in 12044279s — no human required._
