# Postmortem — auth_error

**Cluster:** `ext_61ecf9ac`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-05 10:38:10 UTC |
| Recovery confirmed | 2026-04-09 09:35:46 UTC |
| Time to recovery | **341856s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `RemoteTrigger tool returns 401 due to missing beta/version headers ## Bug Description  The `RemoteTrigger` tool (and rel…`  

**Error:**
```
is presented to the user as a generic `401 Authentication failed`.
```

---

## What Worked

**Tool:** `bash`  
**Input:** `The tool is not sending the required headers:`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 341856s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-05 10:38:10 UTC |
| Last seen | 2026-04-09 09:35:46 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 341856s — no human required._
