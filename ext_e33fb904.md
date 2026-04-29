# Postmortem — configuration_error

**Cluster:** `ext_e33fb904`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-09-23 15:44:49 UTC |
| Recovery confirmed | 2026-04-14 11:43:14 UTC |
| Time to recovery | **17524705s** |

---

## What Broke

**Tool:** `api_call`  
**Input:** `Cline JetBrains plugin ignores proxy settings. ### Plugin Type  JetBrains Plugin  ### Cline Version  3.28.0  ### What ha…`  

**Error:**
```
### Plugin Type  JetBrains Plugin  ### Cline Version  3.28.0  ### What happened?  Cline in IntelliJ IDEA have no way to use system proxy (or any http proxy).  ### Steps to reproduce  1. Get some proxy
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 17524705s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-09-23 15:44:49 UTC |
| Last seen | 2026-04-14 11:43:14 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: configuration_error in api_call is recoverable via unknown in 17524705s — no human required._
