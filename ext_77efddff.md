# Postmortem — auth_error

**Cluster:** `ext_77efddff`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-03 23:30:54 UTC |
| Recovery confirmed | 2026-02-03 18:26:15 UTC |
| Time to recovery | **2660121s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `error  Type: <b>Bug</b>  unnown error  Extension version: 3.46.1 VS Code version: Code 1.107.1 (994fd12f8d3a5aa16f17d42c…`  

**Error:**
```
Extension version: 3.46.1
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2660121s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-03 23:30:54 UTC |
| Last seen | 2026-02-03 18:26:15 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 2660121s — no human required._
