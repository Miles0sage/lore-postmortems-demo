# Postmortem — dependency_error

**Cluster:** `ext_c2a6cbb0`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2025-11-20 04:11:25 UTC |
| Recovery confirmed | 2026-04-22 10:48:04 UTC |
| Time to recovery | **13242999s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `Regression: command execution quoting on Windows ("cmd /c dir" error) ### Plugin Type  VSCode Extension  ### Cline Versi…`  

**Error:**
```
### Plugin Type  VSCode Extension  ### Cline Version  3.38.1  ### What happened?  ### **Summary**  On the latest Cline release, **all command execution fails on Windows**.   Cline is wrapping commands
```

---

## What Worked

**Tool:** `bash`  
**Input:** `introduced in the most recent update.`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 13242999s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2025-11-20 04:11:25 UTC |
| Last seen | 2026-04-22 10:48:04 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: dependency_error in bash is recoverable via bash in 13242999s — no human required._
