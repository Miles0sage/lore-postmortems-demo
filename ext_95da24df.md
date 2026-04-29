# Postmortem — timeout_error

**Cluster:** `ext_95da24df`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-21 07:32:39 UTC |
| Recovery confirmed | 2026-04-24 09:36:43 UTC |
| Time to recovery | **266644s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Feature Request] Provide claude-3-5-opus model option or revert to previous version **Bug Description** give me back Op…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/Lh/.local/share/claude/versions/2.1.114 (expected in multi-process scenarios)\n    at sd_ (/$bunfs/root/src/entrypoints/cli.js:2751:2177
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 266644s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-21 07:32:39 UTC |
| Last seen | 2026-04-24 09:36:43 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: timeout_error in bash is recoverable via unknown in 266644s — no human required._
