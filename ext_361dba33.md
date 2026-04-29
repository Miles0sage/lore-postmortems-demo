# Postmortem — agent_loop

**Cluster:** `ext_361dba33`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-01-12 16:24:07 UTC |
| Recovery confirmed | 2026-01-13 00:54:05 UTC |
| Time to recovery | **30598s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Startup command from2 plugins interfere when cline opens new terminal ### Plugin Type  VSCode Extension  ### Cline Versi…`  

**Error:**
```
### Plugin Type  VSCode Extension  ### Cline Version  v3.49.0  ### What happened?  When cline tries to lunch a new terminal, it never works in python project, It executes a combination of two commands
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 30598s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-01-12 16:24:07 UTC |
| Last seen | 2026-01-13 00:54:05 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: agent_loop in bash is recoverable via unknown in 30598s — no human required._
