# Postmortem — auth_error

**Cluster:** `ext_31b98c5f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-18 06:27:13 UTC |
| Recovery confirmed | 2026-01-26 20:34:05 UTC |
| Time to recovery | **742012s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `AzureOpenAI Identity configuration is pointed to only Azure Commercial ### Plugin Type  VSCode Extension  ### Cline Vers…`  

**Error:**
```
6. Cline returns with the following error
```

---

## What Worked

**Tool:** `read_file`  
**Input:** `logic to handle different audience scopes`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 742012s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-18 06:27:13 UTC |
| Last seen | 2026-01-26 20:34:05 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via read_file in 742012s — no human required._
