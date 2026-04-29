# Postmortem — auth_error

**Cluster:** `ext_d8dbc22a`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-01 22:28:08 UTC |
| Recovery confirmed | 2026-04-05 09:18:01 UTC |
| Time to recovery | **298193s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Model not respecting recorded memories in context and/or `/feedback` not working? **Bug Description** Initial issu…`  

**Error:**
```
[{"error":"AxiosError: Request failed with status code 400\n    at mg (/$bunfs/root/src/entrypoints/cli.js:108:1194)\n    at <anonymous> (/$bunfs/root/src/entrypoints/cli.js:113:12754)\n    at emit (n
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 298193s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-01 22:28:08 UTC |
| Last seen | 2026-04-05 09:18:01 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 298193s — no human required._
