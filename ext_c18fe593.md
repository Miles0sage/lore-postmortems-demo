# Postmortem — auth_error

**Cluster:** `ext_c18fe593`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-25 04:33:15 UTC |
| Recovery confirmed | 2026-04-26 00:51:43 UTC |
| Time to recovery | **73108s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Anthropic API Error: Model claude-3-5-sonnet-20241022 not available on account tier **Bug Description** effort xhi…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /home/tmoney/.local/share/claude/versions/2.1.104 (expected in multi-process scenarios)\n    at KQ$ (/$bunfs/root/src/entrypoints/cli.js:2838:2
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 73108s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-25 04:33:15 UTC |
| Last seen | 2026-04-26 00:51:43 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via unknown in 73108s — no human required._
