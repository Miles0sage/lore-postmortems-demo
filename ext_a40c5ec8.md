# Postmortem — timeout_error

**Cluster:** `ext_a40c5ec8`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-12-08 08:40:47 UTC |
| Recovery confirmed | 2025-12-08 15:29:44 UTC |
| Time to recovery | **24537s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Crash: Healthcheck timed out ### Plugin Type  JetBrains Plugin  ### Cline Version  1.1.3  ### What happened?  Failed to …`  

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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 24537s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-12-08 08:40:47 UTC |
| Last seen | 2025-12-08 15:29:44 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 24537s — no human required._
