# Postmortem — schema_validation_error

**Cluster:** `ext_8f95b6e7`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-19 09:38:27 UTC |
| Recovery confirmed | 2026-03-24 18:21:52 UTC |
| Time to recovery | **2882605s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Wrong location for the cli config file ### Before submitting your bug report  - [x] I've tried using the "Ask AI" featur…`  

**Error:**
```
Fatal error: Failed to load config from "./rules/config.yaml": Error: ENOENT: no such file or directory, open 'C:\Projects\local-LLM\rules\rules\config.yaml'
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2882605s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-19 09:38:27 UTC |
| Last seen | 2026-03-24 18:21:52 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: schema_validation_error in bash is recoverable via unknown in 2882605s — no human required._
