# Postmortem — hallucination

**Cluster:** `ext_3112ab3b`  
**Severity:** LOW (n_observations: 1)  
**Harvested:** 2026-04-29 06:52:48 UTC

---

## Timeline

| Event | Time |
|-------|------|
| Failure detected | 2026-04-21 06:26:17 UTC |
| Recovery confirmed | 2026-04-24 08:24:35 UTC |
| Time to recovery | **266298s** |

---

## What Broke

**Tool:** `bash`  
**Input:** `[Bug]   Compact/resume replays stale slash-command ARGUMENTS as current turn **Bug Description**  Compact/resume re-inje…`  

**Error:**
```
[{"error":"Error: NON-FATAL: Lock acquisition failed for /Users/<redacted>.local/share/claude/versions/2.1.112 (expected in multi-process scenarios)\n    at Od_ (/$bunfs/root/src/entrypoints/cli.js:27
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
Each instance required tool-switching to recover. Without automated routing, each occurrence adds 266298s of latency and risks stalling the agent.

---

## Context

| Field | Value |
|-------|-------|
| Session | `None` |
| Working dir | `None` |
| Git branch | `None` |
| First seen | 2026-04-21 06:26:17 UTC |
| Last seen | 2026-04-24 08:24:35 UTC |

---

## Source

`/root/claude-brain/dpo-pairs/2026-04-29.public-corpus.jsonl`

---

_Lesson Lore would route around: hallucination in bash is recoverable via unknown in 266298s — no human required._
