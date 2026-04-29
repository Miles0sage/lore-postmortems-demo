# Postmortem — auth_error

**Cluster:** `ext_5b02ac6e`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-17 06:06:34 UTC |
| Recovery confirmed | 2026-03-17 11:17:53 UTC |
| Time to recovery | **18679s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] `downloads.claude.ai` returning 403 — Cowork workspace fails to start, update check broken (macOS) ### Preflight C…`  

**Error:**
```
2026-03-17 06:36:14 [error] [CCD] Download attempt 2/3 failed Error: Download failed with status code: 403
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 18679s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-17 06:06:34 UTC |
| Last seen | 2026-03-17 11:17:53 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 18679s — no human required._
