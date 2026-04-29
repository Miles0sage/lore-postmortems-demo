# Postmortem — auth_error

**Cluster:** `ext_b2d6e65d`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-20 12:44:32 UTC |
| Recovery confirmed | 2026-04-24 09:40:52 UTC |
| Time to recovery | **334580s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Text-to-Speech reads record symbol "⏺" as "Record Media Symbol" instead of being silent **Bug Description** Using …`  

**Error:**
```
[{"error":"AxiosError: Request failed with status code 401\n    at XU (/$bunfs/root/src/entrypoints/cli.js:110:1194)\n    at <anonymous> (/$bunfs/root/src/entrypoints/cli.js:115:12736)\n    at emit (n
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 334580s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-20 12:44:32 UTC |
| Last seen | 2026-04-24 09:40:52 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 334580s — no human required._
