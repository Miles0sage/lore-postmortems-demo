# Postmortem — auth_error

**Cluster:** `ext_75cda1ab`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-13 07:13:14 UTC |
| Recovery confirmed | 2026-03-20 10:16:36 UTC |
| Time to recovery | **615802s** |

---

## What Broke

**Tool:** `read_file`  
**Input:** `[BUG] ### Preflight Checklist  - [x] I have searched [existing issues](https://github.com/anthropics/claude-code/issues?…`  

**Error:**
```
2026-03-13 15:07:29.165 [info] From claude: 2026-03-13T07:07:29.151Z [ERROR] "Error: Error: {\"message\":\"Failed to export 1 events (status=403, code=ERR_BAD_REQUEST, Request failed with status code
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 615802s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-13 07:13:14 UTC |
| Last seen | 2026-03-20 10:16:36 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in read_file is recoverable via unknown in 615802s — no human required._
