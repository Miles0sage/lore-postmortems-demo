# Postmortem — auth_error

**Cluster:** `ext_aafe5e7f`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-21 15:26:24 UTC |
| Recovery confirmed | 2026-04-25 09:23:07 UTC |
| Time to recovery | **323803s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Persistent authentication required despite previous login attempts **Bug Description** I have problem with Cluade …`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/vldk/.local/share/claude/versions/2.1.116 (expected in multi-process scenarios)\n    at jl_ (/$bunfs/root/src/entrypoints/cli.js:2752:21
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 323803s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-21 15:26:24 UTC |
| Last seen | 2026-04-25 09:23:07 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 323803s — no human required._
