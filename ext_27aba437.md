# Postmortem — auth_error

**Cluster:** `ext_27aba437`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-15 16:33:23 UTC |
| Recovery confirmed | 2026-04-19 09:22:20 UTC |
| Time to recovery | **319737s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Claude hallucinates paper content when fetch fails, generates recommendations based on fabricated data **Bug Descr…`  

**Error:**
```
[{"error":"AxiosError: Request failed with status code 403\n    at tF (/$bunfs/root/src/entrypoints/cli.js:110:1194)\n    at <anonymous> (/$bunfs/root/src/entrypoints/cli.js:115:12744)\n    at emit (n
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 319737s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-15 16:33:23 UTC |
| Last seen | 2026-04-19 09:22:20 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 319737s — no human required._
