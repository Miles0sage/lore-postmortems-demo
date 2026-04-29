# Postmortem — auth_error

**Cluster:** `ext_eb1a0b13`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-01-30 11:26:38 UTC |
| Recovery confirmed | 2025-04-19 21:55:24 UTC |
| Time to recovery | **6863326s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Github server: Allow it to figure out and remember who the Github user is. **Is your feature request related to a proble…`  

**Error:**
```
throw new Error(`Failed to fetch authenticated user: ${response.statusText}`);
```

---

## What Worked

**Tool:** `bash`  
**Input:** `Automatically Determine the GitHub User**`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 6863326s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-01-30 11:26:38 UTC |
| Last seen | 2025-04-19 21:55:24 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 6863326s — no human required._
