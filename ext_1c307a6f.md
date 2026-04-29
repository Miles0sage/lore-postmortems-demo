# Postmortem — auth_error

**Cluster:** `ext_1c307a6f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-01 19:24:54 UTC |
| Recovery confirmed | 2026-04-05 09:18:38 UTC |
| Time to recovery | **309224s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] CLI output truncated on right side in iTerm2 **Bug Description** The buddy gets cut of to the right on ITerm2.  **…`  

**Error:**
```
[{"error":"AxiosError: Request failed with status code 403\n    at mg (/$bunfs/root/src/entrypoints/cli.js:108:1194)\n    at <anonymous> (/$bunfs/root/src/entrypoints/cli.js:113:12754)\n    at emit (n
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 309224s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-01 19:24:54 UTC |
| Last seen | 2026-04-05 09:18:38 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 309224s — no human required._
