# Postmortem — auth_error

**Cluster:** `ext_9ea744e5`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-13 06:33:44 UTC |
| Recovery confirmed | 2026-04-16 09:35:33 UTC |
| Time to recovery | **270109s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Unintended data loss from unsafe git operations **Bug Description** DATALOSS CAUSED BY SLOPPY GIT BEHAVIOUR  **Env…`  

**Error:**
```
[{"error":"Error: Executable not found in $PATH: \"pyright-langserver\"\n    at spawn (unknown)\n    at spawn (node:child_process:667:35)\n    at spawn (node:child_process:14:39)\n    at start (/$bunf
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 270109s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-13 06:33:44 UTC |
| Last seen | 2026-04-16 09:35:33 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 270109s — no human required._
