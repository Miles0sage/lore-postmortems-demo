# Postmortem — network_error

**Cluster:** `ext_dc76c111`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-04-12 11:38:09 UTC |
| Recovery confirmed | 2025-12-23 19:58:48 UTC |
| Time to recovery | **22062039s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `API Request Failed: Connection error. ### What happened?  Getting this error every time, on any new project. While it co…`  

**Error:**
```
every time, on any new project. While it continues to work on an another existing project.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 22062039s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-04-12 11:38:09 UTC |
| Last seen | 2025-12-23 19:58:48 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: network_error in bash is recoverable via unknown in 22062039s — no human required._
