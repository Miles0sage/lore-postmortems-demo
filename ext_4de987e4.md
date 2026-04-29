# Postmortem — auth_error

**Cluster:** `ext_4de987e4`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-11 10:36:14 UTC |
| Recovery confirmed | 2026-04-14 22:19:45 UTC |
| Time to recovery | **301411s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `[BUG] Claude for Excel — "Work across files" MCP proxy returns 401 authentication error ### Preflight Checklist  - [x] I…`  

**Error:**
```
I can't find any helps from your support team. THerefore I have to report here. You may mark Invalid but I do need help with Claude and NO ONE is supporting me. I'll keep posting until you take notice
```

---

## What Worked

**Tool:** `read_file`  
**Input:** `storage-blocking errors but 401 persists)`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 301411s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-11 10:36:14 UTC |
| Last seen | 2026-04-14 22:19:45 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via read_file in 301411s — no human required._
