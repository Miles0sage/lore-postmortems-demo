# Postmortem — timeout_error

**Cluster:** `ext_45344acf`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-29 14:12:55 UTC |
| Recovery confirmed | 2026-04-23 10:25:21 UTC |
| Time to recovery | **12514346s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Cline Core fails to start on Android Studio Otter (2025.2.1) – “Healthcheck timed out” ### Plugin Type  JetBrains Plugin…`  

**Error:**
```
Healthcheck timed out
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 12514346s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-29 14:12:55 UTC |
| Last seen | 2026-04-23 10:25:21 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 12514346s — no human required._
