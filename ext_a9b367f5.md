# Postmortem — auth_error

**Cluster:** `ext_a9b367f5`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-07 09:54:31 UTC |
| Recovery confirmed | 2026-04-11 09:21:17 UTC |
| Time to recovery | **343606s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Agent executes destructive commands without safety validation or backup **Bug Description** Agent behavior quality…`  

**Error:**
```
[{"error":"AxiosError: Request failed with status code 403\n    at vB (B:/~BUN/root/src/entrypoints/cli.js:108:1194)\n    at <anonymous> (B:/~BUN/root/src/entrypoints/cli.js:113:12750)\n    at emit (n
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 343606s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-07 09:54:31 UTC |
| Last seen | 2026-04-11 09:21:17 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 343606s — no human required._
