# Postmortem — auth_error

**Cluster:** `ext_097f77de`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-12-07 07:49:48 UTC |
| Recovery confirmed | 2025-04-19 21:56:25 UTC |
| Time to recovery | **11541997s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `GitHub API error: Unprocessable Entity when creating PR between two unrelated branches ## Issue Description When trying …`  

**Error:**
```
throw new Error(`Failed to compare branches: ${compareResponse.statusText}`);
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 11541997s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-12-07 07:49:48 UTC |
| Last seen | 2025-04-19 21:56:25 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 11541997s — no human required._
