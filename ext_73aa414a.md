# Postmortem — auth_error

**Cluster:** `ext_73aa414a`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-06 15:53:45 UTC |
| Recovery confirmed | 2026-04-28 05:57:41 UTC |
| Time to recovery | **1865036s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `OAuth login: CLI times out waiting for callback despite successful browser authorization ## Description  After clicking …`  

**Error:**
```
Request failed with status code 500`
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 1865036s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-06 15:53:45 UTC |
| Last seen | 2026-04-28 05:57:41 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 1865036s — no human required._
