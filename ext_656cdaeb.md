# Postmortem — auth_error

**Cluster:** `ext_656cdaeb`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-25 23:53:48 UTC |
| Recovery confirmed | 2026-04-27 22:24:47 UTC |
| Time to recovery | **2845859s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[BUG] CLI hangs silently on WSL2 - streaming response never processed ## Description  Claude Code CLI hangs indefinitely…`  

**Error:**
```
message. Affects interactive mode and `claude -p`.
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2845859s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-25 23:53:48 UTC |
| Last seen | 2026-04-27 22:24:47 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 2845859s — no human required._
