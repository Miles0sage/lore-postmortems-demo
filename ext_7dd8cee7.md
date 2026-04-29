# Postmortem — timeout_error

**Cluster:** `ext_7dd8cee7`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-12 13:57:16 UTC |
| Recovery confirmed | 2026-01-13 00:57:29 UTC |
| Time to recovery | **39613s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Pycharm ### Plugin Type  JetBrains Plugin  ### Cline Version  1.1.19  ### What happened?  Failed to load Cline  Healthch…`  

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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 39613s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-12 13:57:16 UTC |
| Last seen | 2026-01-13 00:57:29 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 39613s — no human required._
