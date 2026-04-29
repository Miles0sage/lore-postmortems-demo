# Postmortem — auth_error

**Cluster:** `ext_2c80f4de`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-09 14:25:25 UTC |
| Recovery confirmed | 2026-04-13 09:43:38 UTC |
| Time to recovery | **328693s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Excessive token consumption and latency on single-word prompts **Bug Description** I hate to report as a 1(bad) be…`  

**Error:**
```
[{"error":"AxiosError: Request failed with status code 400\n    at ig (/$bunfs/root/src/entrypoints/cli.js:108:1194)\n    at <anonymous> (/$bunfs/root/src/entrypoints/cli.js:113:12750)\n    at emit (n
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 328693s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-09 14:25:25 UTC |
| Last seen | 2026-04-13 09:43:38 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 328693s — no human required._
