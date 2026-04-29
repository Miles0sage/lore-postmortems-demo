# Postmortem — auth_error

**Cluster:** `ext_1bb6631a`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-02 14:48:19 UTC |
| Recovery confirmed | 2026-03-31 10:27:34 UTC |
| Time to recovery | **2489955s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Remote Control Authentication Failed: Invalid OAuth token with claude.ai login **Bug Description** bogdandobre@192…`  

**Error:**
```
[{"error":"Error: Failed to delete keychain entry\n    at bdB (/$bunfs/root/claude:3653:6018)\n    at async E80 (/$bunfs/root/claude:6284:685)\n    at async nkA (/$bunfs/root/claude:6284:589)\n    at
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2489955s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-02 14:48:19 UTC |
| Last seen | 2026-03-31 10:27:34 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 2489955s — no human required._
