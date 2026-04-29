# Postmortem — resource_not_found

**Cluster:** `ext_00f3cdca`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-04-30 01:39:37 UTC |
| Recovery confirmed | 2025-08-01 19:17:46 UTC |
| Time to recovery | **8098689s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Time server fails for WEST times **Describe the bug** Time server doesn't work in Portugal. Assume WEST times are not pr…`  

**Error:**
```
**Expected behavior**
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 8098689s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-04-30 01:39:37 UTC |
| Last seen | 2025-08-01 19:17:46 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: resource_not_found in bash is recoverable via unknown in 8098689s — no human required._
