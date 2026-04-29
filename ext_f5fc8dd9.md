# Postmortem — auth_error

**Cluster:** `ext_f5fc8dd9`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-03-18 15:00:02 UTC |
| Recovery confirmed | 2026-04-15 22:21:20 UTC |
| Time to recovery | **2445678s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug] Anthropic API Error: Invalid JWT in Edge Function authentication **Bug Description** claude didnt succeed in fixin…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/massimo/.local/share/claude/versions/2.1.78 (expected in multi-process scenarios)\n    at gVT (/$bunfs/root/src/entrypoints/cli.js:2648:
```

---

## What Worked

**Tool:** `bash`  
**Input:** `applied: openaiConfig.ts (line 24) now explicitly:`  

**Result (truncated):**
```
resolved
```

---

## Why It Matters

This failure pattern has been observed **1 time(s)** across multiple sessions.  
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 2445678s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-03-18 15:00:02 UTC |
| Last seen | 2026-04-15 22:21:20 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: auth_error in bash is recoverable via bash in 2445678s — no human required._
