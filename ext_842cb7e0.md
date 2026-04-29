# Postmortem — auth_error

**Cluster:** `ext_842cb7e0`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-07-06 21:05:57 UTC |
| Recovery confirmed | 2025-08-04 02:17:56 UTC |
| Time to recovery | **2437919s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `server-gdrive 'auth' command fails to find credentials **Describe the bug** When running `npx @modelcontextprotocol/serv…`  

**Error:**
```
Cannot find module '/Users/quantum_rt_server/.npm/_npx/901beb8b1a496dd2/node_modules/gcp-oauth.keys.json'
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2437919s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-07-06 21:05:57 UTC |
| Last seen | 2025-08-04 02:17:56 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 2437919s — no human required._
