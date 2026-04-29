# Postmortem — context_overflow

**Cluster:** `ext_b585c05b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-11 07:08:15 UTC |
| Recovery confirmed | 2026-04-09 21:46:18 UTC |
| Time to recovery | **12926283s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Why does using "@" to select a folder submit all the file content codes ### Plugin Type  JetBrains Plugin  ### Cline Ver…`  

**Error:**
```
except Exception as e:
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 12926283s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-11 07:08:15 UTC |
| Last seen | 2026-04-09 21:46:18 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: context_overflow in bash is recoverable via unknown in 12926283s — no human required._
