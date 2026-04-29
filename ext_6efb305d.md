# Postmortem — timeout_error

**Cluster:** `ext_6efb305d`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-13 19:00:20 UTC |
| Recovery confirmed | 2026-04-17 09:37:45 UTC |
| Time to recovery | **311845s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Unreliable connection handling causing stalls and timeouts **Bug Description** All the time connection problems, s…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /home/othmar-atzmueller/.local/share/claude/versions/2.1.104 (expected in multi-process scenarios)\n    at KQ$ (/$bunfs/root/src/entrypoints/cl
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 311845s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-13 19:00:20 UTC |
| Last seen | 2026-04-17 09:37:45 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 311845s — no human required._
