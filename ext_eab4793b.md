# Postmortem — general_failure

**Cluster:** `ext_eab4793b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2024-12-22 22:07:48 UTC |
| Recovery confirmed | 2025-08-17 22:23:09 UTC |
| Time to recovery | **20564121s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `Does the file system server really support resources? **Describe the bug** The filesystem server claims it supports the…`  

**Error:**
```
**Describe the bug** The filesystem server claims it supports the resources capability (https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem#resources) However, I cannot see this
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 20564121s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2024-12-22 22:07:48 UTC |
| Last seen | 2025-08-17 22:23:09 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: general_failure in read_file is recoverable via unknown in 20564121s — no human required._
