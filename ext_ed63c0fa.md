# Postmortem — timeout_error

**Cluster:** `ext_ed63c0fa`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-02-11 10:43:16 UTC |
| Recovery confirmed | 2026-02-16 22:03:34 UTC |
| Time to recovery | **472818s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `'Shell integration timeout' setting reverts to 4 seconds ### Plugin Type  VSCode Extension  ### Cline Version  0.0.68  #…`  

**Error:**
```
### Plugin Type  VSCode Extension  ### Cline Version  0.0.68  ### What happened?  I am reporting an issue with the Sixth plugin where I am unable to modify the 'Shell integration timeout (seconds)' se
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 472818s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-02-11 10:43:16 UTC |
| Last seen | 2026-02-16 22:03:34 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 472818s — no human required._
